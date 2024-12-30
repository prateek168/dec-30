# SmartReach Marketing Hub

## Core Components

### Campaign Modules
- `PersonalizedCampaigns`: Existing customer targeting
- `NewCustomerAdmin`: Admin-managed acquisition campaigns
- `NewCustomerInfluencer`: Influencer campaign management 
- `Membership`: Tier management + benefits
- `LoyaltyPrograms`: Points/rewards system
- `ReferralPrograms`: Referral tracking + rewards 
- `AutoBirthday`: Birthday offer triggers
- `AutoAnniversary`: Anniversary campaign handling
- `AutoInactive`: Re-engagement flow 
- `WhatsAppChat`: Customer messaging interface
- `Refill`: Inventory management system

###`PersonalizedCampaigns`: 
### `PersonalizedCampaigns`: 
Targets existing customers with tailored campaigns.

#### 1. **View Offers**
- **Running Offers**: Active campaigns.
- **Scheduled Offers**: Upcoming campaigns.
- **Previous Offers**: Past campaigns.

#### 2. **Create Offers**
- **Customer Details**:
  - **Targeting**: All Order Types | Specialized Dining Customers.
  - **Date Options**: Last Week | Last Month | Custom Date Range.
  - **Time Range**: Start Time | End Time.
  - **Order Types**: Dining | Parcel | Zomato/Swiggy | Self-Online Delivery.
  - **Location**: State | City.
  - **Food Type**: Veg | Non-Veg.
  - **Total Bill Range**: Min Price | Max Price.
  - **Preview Option**: View before submission.
  - **Submit**: Finalize offer.
  <br>
  
  ```
   const customerDetailsSchema = new mongoose.Schema({
      target: {
          type: String,
          enum: ['AllOrderTypes', 'SpecializedDiningCustomers'],
          required: true
      },
      dateOptions: {
          type: String,
          enum: ['LastWeek', 'LastMonth', 'CustomDateRange'],
          required: true
      },
      timeRange: {
          startTime: { type: String, required: true },
          endTime: { type: String, required: true }
      },
      orderTypes: {
          type: [String],
          enum: ['Dining', 'Parcel', 'Zomato/Swiggy', 'SelfOnlineDelivery'],
          required: true
      },
      location: {
          state: { type: String, required: true },
          city: { type: String, required: true }
      },
      foodType: {
          type: String,
          enum: ['Veg', 'NonVeg'],
          required: true
      },
      totalBillRange: {
          minPrice: { type: Number, required: true },
          maxPrice: { type: Number, required: true }
      },
      previewOption: { type: Boolean, required: true },
      submitButton: { type: Boolean, required: true } });
  ```
  
- **Coupon Details**:
  - **Coupon Name**: Name of the offer.
  - **Validity Dates**: Start & End dates.
  - **Membership Applicability**: Yes/No.
  - **Usage Limits**: Total Uses | Per Phone Number (Unlimited | Custom Input).
  - **Discount**: Percentage off.
  - **Min Order Value**: Minimum required order.
  - **Send Message**: Immediately | Scheduled.
   <br>
 
   
    ```
    const couponDetailsSchema = new mongoose.Schema({
    couponName: { type: String, required: true },
    validityDates: {
        start: { type: Date, required: true },
        end: { type: Date, required: true }
    },
    applicabilityForMembership: { type: Boolean, required: true },
    numberOfTimesUsed: {
        type: String,
        enum: ['Unlimited', 'Custom'],
        required: true
    },
    numberOfTimesUsedPerPhone: {
        type: String,
        enum: ['Unlimited', 'Custom'],
        required: true
    },
    discountOnFoodOrdering: { type: Number, required: true },
    minOrderValue: { type: Number, required: true },
    sendMessage: {
        type: String,
        enum: ['Immediately', 'Scheduled'],
        required: true
    }});
    ```
  

```mermaid
classDiagram
    MarketingSection --> PersonalizedCampaigns
    MarketingSection --> Refil
    MarketingSection --> WhatsAppChat
    MarketingSection --> NewCustomerCampaignsAdmin
    MarketingSection --> NewCustomerCampaignsInfluencer
    MarketingSection --> Membership
    MarketingSection --> LoyaltyPrograms
    MarketingSection --> ReferralPrograms
    MarketingSection --> AutomatedOffersBirthday
    MarketingSection --> AutomatedOffersAnniversary
    MarketingSection --> AutomatedOffersInactiveCustomers

    class MarketingSection {
        +PersonalizedCampaigns
        +NewCustomerCampaignsAdmin
        +NewCustomerCampaignsInfluencer
        +Membership
        +LoyaltyPrograms
        +ReferralPrograms
        +AutomatedOffersBirthday
        +AutomatedOffersAnniversary
        +AutomatedOffersInactiveCustomers
        +Refil
        +WhatsAppChat
    }

    class PersonalizedCampaigns {
        +ViewOffers()
        +CreateOffers()
    }

    class Refil {
        +SMS25k
        +SMS50k
        +SMS100k
        +Custom
    }

    class WhatsAppChat {
        +SendMessage()
    }

    class NewCustomerCampaignsAdmin {
        +CreateCampaign()
        +TargetingAdmin()
    }

    class NewCustomerCampaignsInfluencer {
        +CreateCampaign()
        +TargetingInfluencer()
    }

    class Membership {
        +JoinMembership()
        +RenewMembership()
    }

    class LoyaltyPrograms {
        +EarnPoints()
        +RedeemPoints()
    }

    class ReferralPrograms {
        +ReferFriend()
        +TrackReferrals()
    }

    class AutomatedOffersBirthday {
        +SendBirthdayOffer()
    }

    class AutomatedOffersAnniversary {
        +SendAnniversaryOffer()
    }

    class AutomatedOffersInactiveCustomers {
        +SendOfferToInactiveCustomers()
    }

    class CouponDetails {
        +CouponName: String
        +ValidityDates: DateRange
        +ApplicabilityForMembership: Boolean
        +NumberOfTimesUsed: String[Unlimited|CustomInput]
        +NumberOfTimesUsedPerPhone: String[Unlimited|CustomInput]
        +DiscountOnFoodOrdering: Number
        +MinOrderValue: Number
        +SendMessage: String[Immediately|Scheduled]
    }

    class CustomerDetails {
        +Target: String[AllOrderTypes|SpecializedDiningCustomers]
        +DateOptions: String[LastWeek|LastMonth|CustomDateRange]
        +TimeRange: String[StartTime-EndTime]
        +OrderTypes: String[Dining|Parcel|Zomato/Swiggy|SelfOnlineDelivery]
        +Location: String[State|City]
        +FoodType: String[Veg|NonVeg]
        +TotalBillRange: Number[MinPrice-MaxPrice]
        +PreviewOption()
        +SubmitButton()
    }

    class ViewOffers {
        +Running()
        +Scheduled()
        +Previous()
    }

    CreateOffers --> CustomerDetails
    CreateOffers --> CouponDetails
    PersonalizedCampaigns --> ViewOffers
    PersonalizedCampaigns --> CreateOffers

```

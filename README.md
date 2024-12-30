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
    class PersonalizedCampaigns {
        +ViewOffers()
        +CreateOffers()
    }
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


    class ViewOffers {
        +Running()
        +Scheduled()
        +Previous()
    }

    class CreateOffers {
        +CustomerDetails
        +CouponDetails
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

    PersonalizedCampaigns --> ViewOffers
    PersonalizedCampaigns --> CreateOffers
    CreateOffers --> CustomerDetails
    CreateOffers --> CouponDetails
    MarketingSection --> PersonalizedCampaigns

 ```

# Routes Documentation for SmartReach Marketing Hub

## 1. **POST /createOffer**
This route is used to create a new personalized campaign offer with customer and coupon details.

**Request Body**:
```json
{
  "customerDetails": {
    "target": "AllOrderTypes", 
    "dateOptions": "LastWeek", 
    "timeRange": { "startTime": "2024-12-01T00:00", "endTime": "2024-12-07T23:59" },
    "orderTypes": ["Dining", "Parcel"],
    "location": { "state": "California", "city": "Los Angeles" },
    "foodType": "Veg",
    "totalBillRange": { "minPrice": 100, "maxPrice": 500 },
    "previewOption": true,
    "submitButton": true
  },
  "couponDetails": {
    "couponName": "HolidayDiscount",
    "validityDates": { "start": "2024-12-01", "end": "2024-12-31" },
    "applicabilityForMembership": true,
    "numberOfTimesUsed": "Unlimited",
    "numberOfTimesUsedPerPhone": "Custom",
    "discountOnFoodOrdering": 20,
    "minOrderValue": 200,
    "sendMessage": "Scheduled"
  }
}
```
## 2. **GET /viewOffers**
This route is used to fetch and view the available personalized campaign offers.

**Query Parameters**:
```
- **type** (required): The type of offers you want to view. Options include:
  - `running`: Active campaigns that are currently running.
  - `scheduled`: Upcoming campaigns that are scheduled to start in the future.
  - `previous`: Past campaigns that have ended.
```
Example: To view running offers, use the query parameter `?type=running`.

**Example Request**:

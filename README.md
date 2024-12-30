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
  
- **Coupon Details**:
  - **Coupon Name**: Name of the offer.
  - **Validity Dates**: Start & End dates.
  - **Membership Applicability**: Yes/No.
  - **Usage Limits**: Total Uses | Per Phone Number (Unlimited | Custom Input).
  - **Discount**: Percentage off.
  - **Min Order Value**: Minimum required order.
  - **Send Message**: Immediately | Scheduled.
 

[![](https://mermaid.ink/img/pako:eNqVV99v4jgQ_ldQnu50pUdo6bZ5OInCVuppKajp7kq79MFNhmDVsSPHaTdb-r_v2CnBJoEWXpx4vvnmp8fhxYtEDF7gRYzk-ZiSRJJ0zjv4mxD5CIryJIRIUcE73e5_nRnIXHDC6G-IRyTNCE14vgd_CwvK9si_L4nKh1k2wnUP7AaeR0WuRAqytjqMU8oP1LnmC1YAj0DuUZxA-oBhLmm2B_RFlISpciaFztg7KQApCfsAdFigu0RBPF2gTn5JpVrGpPy4xpBz-oQrkQcoXXOCsidYZws9rJRNTzQpXiqp_v2zpx-M_J3C7cRsF8oAtwtjNlsLYSTtiTeivYluQzQS2wZqSaTtzPogmPdm47-6aW_NrJP7bxSeK8N__W1tjySgS65gi9s443CFk7A_eHQ3Br2tDb_n7FRhthqwo3PtAI8nkOckgR2-7ewYh6cKcg1w4r8jMjH9arQOsLLpuYNNbVR32Nu0rsP9v6B8I3K4b4HDc1O2xbvV_Q75ZyL5DA2ofIs4BkhdQbM_nJPj0BrhlaRYSTcZkkSPa81dzDsOXqNH1gID-xiXdUQbdJbsAMbGeW7wGtydaAB38I9EkQk-BkUoc8kqyQ1JIeiESmJL2Qcdp0BMVTlG1_Kgo5dbwhOwJ1GWMRqRB8oQdyXkpnGCzqUQDIgzcQstnS7uaAr51xzitdGfXzmjKcUMrKpYrnlWqPt9qjinZkvB4eMUY5pHouBqyq-EiKcyBq0XdCpqe95TbqQYfwEtcmuY1Nav0xRiihli5SqMlhAXDOL79mq8VautHtXJrlmHjBlP7soM8lWYQUSryTymHOV13Z0w9RTO9I2Z1zxfSK6-Azyu9MNEcLV8S1JdU5tB59hs1vqhIlLp7e5nHuvVhm88rPGVe6sZkRGw1Q_d3OLf8JkmCWYH2GKKteIwBqZPR3nvXKsR0b7bphWsRtheNkxXUJusYd8gWd0IjosTiVCEXVLG3sKpSvkTCzyTNILuhPwyD7bOTMKTvuFMCp1JExYP2GCXhVJi13zf3I3u7Cq4TojLtu4SZ9dYF0XzJNvXq_ma2mqjXSj76FeY9htegzfev4e07cy5d-ShIymhMX7Rm7jnnlpCCnMvwMcYFqRgau7N-StCCU67sOSRFyhZwJEnRZEsvWCB0xvfiixG5rd_BGtIRvgPIexXL3jxfnlB9-S4d3J2enre7w9Oe_7F2cWRV3qB7_vHA__ThY9bn3rnp_7g9cj7bRj8Y79_fj7wz_onvbO-j6jXPwo1G48?type=png)](https://mermaid.live/edit#pako:eNqVV99v4jgQ_ldQnu50pUdo6bZ5OInCVuppKajp7kq79MFNhmDVsSPHaTdb-r_v2CnBJoEWXpx4vvnmp8fhxYtEDF7gRYzk-ZiSRJJ0zjv4mxD5CIryJIRIUcE73e5_nRnIXHDC6G-IRyTNCE14vgd_CwvK9si_L4nKh1k2wnUP7AaeR0WuRAqytjqMU8oP1LnmC1YAj0DuUZxA-oBhLmm2B_RFlISpciaFztg7KQApCfsAdFigu0RBPF2gTn5JpVrGpPy4xpBz-oQrkQcoXXOCsidYZws9rJRNTzQpXiqp_v2zpx-M_J3C7cRsF8oAtwtjNlsLYSTtiTeivYluQzQS2wZqSaTtzPogmPdm47-6aW_NrJP7bxSeK8N__W1tjySgS65gi9s443CFk7A_eHQ3Br2tDb_n7FRhthqwo3PtAI8nkOckgR2-7ewYh6cKcg1w4r8jMjH9arQOsLLpuYNNbVR32Nu0rsP9v6B8I3K4b4HDc1O2xbvV_Q75ZyL5DA2ofIs4BkhdQbM_nJPj0BrhlaRYSTcZkkSPa81dzDsOXqNH1gID-xiXdUQbdJbsAMbGeW7wGtydaAB38I9EkQk-BkUoc8kqyQ1JIeiESmJL2Qcdp0BMVTlG1_Kgo5dbwhOwJ1GWMRqRB8oQdyXkpnGCzqUQDIgzcQstnS7uaAr51xzitdGfXzmjKcUMrKpYrnlWqPt9qjinZkvB4eMUY5pHouBqyq-EiKcyBq0XdCpqe95TbqQYfwEtcmuY1Nav0xRiihli5SqMlhAXDOL79mq8VautHtXJrlmHjBlP7soM8lWYQUSryTymHOV13Z0w9RTO9I2Z1zxfSK6-Azyu9MNEcLV8S1JdU5tB59hs1vqhIlLp7e5nHuvVhm88rPGVe6sZkRGw1Q_d3OLf8JkmCWYH2GKKteIwBqZPR3nvXKsR0b7bphWsRtheNkxXUJusYd8gWd0IjosTiVCEXVLG3sKpSvkTCzyTNILuhPwyD7bOTMKTvuFMCp1JExYP2GCXhVJi13zf3I3u7Cq4TojLtu4SZ9dYF0XzJNvXq_ma2mqjXSj76FeY9htegzfev4e07cy5d-ShIymhMX7Rm7jnnlpCCnMvwMcYFqRgau7N-StCCU67sOSRFyhZwJEnRZEsvWCB0xvfiixG5rd_BGtIRvgPIexXL3jxfnlB9-S4d3J2enre7w9Oe_7F2cWRV3qB7_vHA__ThY9bn3rnp_7g9cj7bRj8Y79_fj7wz_onvbO-j6jXPwo1G48)

# Milestone 1: Smart Grocery Guide

## Domain

My project is a retrieval-augmented grocery shopping assistant that helps users find useful information about major grocery retailers across New York, Maryland, and North Carolina. The knowledge base will focus on store locations, grocery offerings, shopping services, pickup and delivery options, membership requirements, and other retailer-specific information that can help someone decide where and how to shop.

I chose this domain because it connects directly to my Smart Pantry concept, which is designed to help people manage the food they have at home and make better grocery-shopping decisions. Grocery information is often scattered across individual retailer websites, store locators, FAQs, online-ordering pages, and service pages, making it difficult to compare stores in one place. A RAG system gives me an opportunity to build the information-retrieval foundation that could eventually support a larger Smart Pantry grocery-shopping experience.

The first version will intentionally focus on relatively stable retailer information rather than live prices or inventory. Current prices, promotions, and item availability change frequently and would be better handled through retailer APIs or other live data sources in a future version.

## Documents

The initial knowledge base will use authoritative first-party retailer sources. Rather than treating an entire retailer website as one document, I will compile relevant information from multiple official pages into retailer-specific documents during the ingestion phase.

| # | Source | Description | URL |
|---|--------|-------------|-----|
| 1 | Walmart Pickup & Delivery | Information about Walmart grocery pickup and delivery services. | https://www.walmart.com/help/article/pickup-and-delivery/d0d02a5f54e54592930f110aaf6a2f50 |
| 2 | Walmart Store Finder | Store locations and available store services. | https://www.walmart.com/store-finder |
| 3 | Costco Warehouse Locations | Costco warehouse locations and store information. | https://www.costco.com/w/-/locations |
| 4 | Costco Same-Day Grocery Delivery | Same-day grocery delivery information, including delivery requirements and pricing considerations. | https://www.costco.com/f/-/same-day |
| 5 | BJ's Club Locator | BJ's locations, including locations in Maryland, New York, and North Carolina. | https://www.bjs.com/allClubLocator |
| 6 | BJ's Same-Day Delivery | Grocery delivery categories, eligibility, fees, and ordering information. | https://www.bjs.com/about/ordering/same-day-delivery/ |
| 7 | Trader Joe's Store Directory | Trader Joe's store locations by state. | https://locations.traderjoes.com/ |
| 8 | Trader Joe's Pantry Products | Pantry-related product categories and grocery information. | https://www.traderjoes.com/home/products/category/for-the-pantry-137 |
| 9 | Wegmans Store Locator | Wegmans store locations, including locations in NY, MD, and NC. | https://www.wegmans.com/stores |
| 10 | Wegmans Grocery Delivery & Pickup | Grocery pickup, delivery, ordering, fees, and payment information. | https://www.wegmans.com/grocery-delivery-pickup |
| 11 | Food Lion Maryland Locations | Food Lion locations throughout Maryland. | https://stores.foodlion.com/md |
| 12 | Food Lion North Carolina Locations | Food Lion locations throughout North Carolina. | https://stores.foodlion.com/nc |
| 13 | Giant Food Store Locator | Giant Food store locations and services. | https://stores.giantfood.com/index.html |
| 14 | Giant Food Grocery Services | Grocery pickup, delivery, and same-day service information. | https://giantfood.com/our_stores/locator/store_search.htm |
| 15 | ALDI Grocery Pickup | ALDI curbside grocery pickup and ordering information. | https://www.aldi.us/store/aldi/pages/grocery-pickup |
| 16 | ALDI Grocery Delivery | ALDI same-day grocery delivery and ordering information. | https://www.aldi.us/store/aldi/pages/grocery-delivery |
| 17 | Whole Foods Store Locator | Whole Foods Market store locations and store information. | https://www.wholefoodsmarket.com/stores |
| 18 | Whole Foods Online Ordering | Grocery delivery, pickup, online ordering, and grocery services. | https://www.wholefoodsmarket.com/online-ordering |
| 19 | Target Pickup & Delivery | Target Order Pickup, Drive Up, same-day delivery, and grocery services. | https://corporate.target.com/about/products-services/pickup-delivery |
| 20 | Target Drive Up & Order Pickup | Details about Target Drive Up and Order Pickup services. | https://www.target.com/help/articles/delivery-options/drive-up-order-pickup |

## Initial Evaluation Questions

The following questions will be used later to evaluate whether the RAG system retrieves relevant information and generates grounded answers.

| # | Question | Expected answer |
|---|----------|-----------------|
| 1 | Which of the 10 retailers offer grocery pickup, and which offer grocery delivery? | The system should identify retailers whose source documents explicitly document pickup and/or delivery and distinguish between the two services when the sources allow it. |
| 2 | Which of the 10 retailers have locations in North Carolina? | The system should identify the retailers whose source material confirms North Carolina locations. |
| 3 | Which retailers in the knowledge base use a membership-based shopping model? | The expected answer should identify Costco and BJ's Wholesale Club as membership-based retailers. |
| 4 | What grocery pickup and delivery options does Wegmans offer? | The answer should describe the pickup and delivery services documented in Wegmans' official sources, including relevant ordering and service details. |
| 5 | What is the current price of chicken breast at Walmart? | The system should explain that it does not have enough information to answer because the V1 knowledge base does not contain live product pricing. |

## Scope Boundary

The first version of this project will not attempt to provide live product prices, real-time inventory, current promotions, or guaranteed item availability. Those data points are dynamic and would require live retailer data or APIs.

The goal of this project is to build a grounded retrieval system that establishes the information layer for a future grocery-shopping assistant. A future version could connect this RAG system to the Smart Pantry application's inventory and a live retailer/API layer to generate more personalized and current grocery lists.

## Milestone 1 Completion Checklist

- [x] Domain selected
- [x] Domain rationale documented
- [x] 10+ specific sources identified
- [x] Source URLs documented
- [x] 5 evaluation questions defined
- [ ] Commit Milestone 1 to Git

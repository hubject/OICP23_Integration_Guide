
#  Endpoint versus Protocol Versioning explanation

## Endpoint Versioning Description:

Endpoint versioning within each service in OICP (Open InterCharge Protocol) is
implemented to ensure flexibility, stability, and compatibility as the
protocol evolves over time. This practice, serves several key purposes:

  1.  **Backward Compatibility:** Ensures existing clients and systems continue to function without disruption.

  2.  **Smooth Transition:** Facilitates a gradual shift for clients to adopt newer features and improvements at their own pace.

  3.  **Developer-Friendly:** Simplifies development by offering clear and distinct endpoints for different versions of a service.

  4.  **Avoids Dependency Conflicts:** Prevents conflicts when multiple systems rely on different versions of a service.

  5.  **Security and Performance** : Supports security enhancements, bug fixes, and optimizations without affecting existing integrations.

Endpoint versioning plays a vital role in maintaining stable and evolving
services while allowing flexibility for clients and partners to adapt to
changes as needed.

 **OICP 2.3 Endpoints:**

 | Service | Version |
| ----------------- | ----------- |
| eRoamingAuthorization               | 2.1     |
| eRoamingChargeDetailRecord | 2.2   | 
| eRoamingReservation | 1.1   |  
|eRoamingEVSEData |2.3|
|eRoamingEVSEStatus | 2.1|
|eRoamingDynamicPricing | 1.0 |
|eRoamingChargingNotifications | 1.1 |
  
## Protocol Versioning Description:

Protocol versioning in OICP is essential for similar reasons as endpoint
versioning, with the added dimension of managing changes and improvements at
the protocol level. Here's why protocol versioning is necessary within OICP:

  1.  **Interoperability:** Ensures different systems in the EV charging ecosystem can communicate and work together seamlessly.

  2.  **Adaptation to Change:** Allows the protocol to evolve with industry advancements, regulations, and new requirements.

  3.  **Backward Compatibility:** Preserves the functionality of older integrations while introducing new features.

  4.  **Security and Compliance:** Addresses security vulnerabilities and regulatory changes without disrupting existing services.

  5.  **Developer-Friendly:** Provides clear versioning for easier integration and error handling.

The current OICP version Hubject supports is v2.3.


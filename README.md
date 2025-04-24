# Cloud-Computing
🗂️ System Architecture Overview
The diagram illustrates the high-level architecture of the Shares Brokering System and its interaction with external services.

📦 Components:
Shares Client:
Acts as the front-end interface (console or GUI) that interacts directly with the Shares Brokering Web Service to initiate share transactions, view listings, and perform searches.

Shares Brokering Web Service (RESTful):
Core back-end service that:

Manages the shares data stored in JSON format.

Handles buy/sell transactions and share updates.

Provides share search and listing capabilities.

Interfaces with external APIs to enhance functionality.

Currency Conversion RESTful Web Service:
Consumed by the brokering service to perform real-time currency conversions, enabling users to transact in different currencies accurately.

Latest Currency Rate API (External):
A third-party API used to fetch the most recent exchange rates. Its output is cached locally by the brokering service to support offline functionality and reduce dependency on real-time requests.

🔁 Interaction Flow:
The Shares Client sends requests (e.g., buy/sell/share search) to the Shares Brokering Web Service.

For transactions involving currency conversion, the service calls the Currency Conversion RESTful Web Service.

The currency conversion service internally fetches real-time exchange rates from the Latest Currency Rate API and may persist the data for offline use.

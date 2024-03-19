---
description: >-
  The Datalake page provides an overview of the user's data collections and
  offers functionalities to manage and create new collections.
---

# Data Lake

**Existing Collections**

- **Collection Cards**: Each collection is represented by a card displaying essential information.
  - _Details_: Name of the collection, brief description, blockchain network, collection format, and visibility.
  - _Interaction_: Clicking on a collection card navigates to the collection's dedicated page.

### Explore Further

For additional information on viewing existing collections, please consult the [View Collection Page](view-collection.md).

**Create New Collection**

- **Button**: Clicking the "Create New Collection" card opens a modal titled "Create New Data Collection."

**"Create New Data Collection" Modal**

- **Form Fields**:

  - _Collection Name_: Text input field to specify the name of the new collection.
  - _Description_: Text area to provide detailed information about the collection.

    - _Example Description_: "The IoT (m6) London LT56TGH dataset provides real-time and historical data on travel patterns, tourism, and transportation usage in London spanning 2019-2023.\
      The core dataset includes over 5 billion timestamped records across thousands of sensor streams. Key metrics tracked relate to:

      _Transportation usage_: Passenger levels on Tube lines, buses, trains, airports, taxis, roads. Speed/congestion data for roads/tubes. Origin-Destination flows.

      _Tourism activity_: Foot traffic in zones, visitor numbers and wait times at attractions. Hotel occupancy rates and bookings. Restaurant guest numbers and peak hours.

  - _Category_: Dropdown menu to select the category (e.g., Travel and Tourism Data).
  - _Blockchain Network_: Selection field for choosing the blockchain network (e.g., Polygon, Camino, BNB).

- **Submit Button**: Upon completing the form, the "Submit" button creates the new collection.
  - _Functionality_: Validates the input, creates a new collection on the selected blockchain, and dismisses the modal.

### Explore Further

For additional information on creating a new collection, please consult the [Create Collection Page](new-collection.md).

## Summary

We've provided a brief overview of the functionality and options available in the Data Lake feature.

Within the Data Lake, users can view and edit existing collections and create new ones.

The Data Lake is ideal for one-time data selling or subscription-based usage scenarios, where data sellers can regularly update datasets with fresh data, granting buyers instant access to the latest information.

In the Data Lake, sellers can upload data via:

- **Files:** such as csv, xlsx, or json.
- **API Data Stream:** From within third-party applications that have access to [Offsetdata's API Endpoints](/OD-Docs/api/endpoints.md).

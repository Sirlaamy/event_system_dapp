# Event Registration System DApp

## Overview

The Event Registration System DApp allows users to create events, register for events, and query event and registration information. Built using Cartesi’s technology, this system manages event registrations and provides the capability to view all registered events and participants.

## Features

- **Create Events**: Add new events to the system.
- **Register for Events**: Users can register for existing events.
- **Query Events and Registrations**: Retrieve information about events and registrations.

## Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/event-registration-dapp.git
   cd event-registration-dapp
   ```

2. **Install Dependencies**

   ```bash
   npm install
   ```

3. **Set Up Environment Variables**

   Create a `.env` file in the root directory and set the `ROLLUP_HTTP_SERVER_URL` variable to your Cartesi Rollup server URL.

   ```env
   ROLLUP_HTTP_SERVER_URL=http://your-rollup-server-url
   ```

4. **Run the DApp**

   ```bash
   node index.js
   ```

## Endpoints

- **Creating Events**
  - **`POST /advance`**: Create a new event. The payload should include an action of `create_event` and the event details.

- **Registering for Events**
  - **`POST /advance`**: Register for an event. The payload should include an action of `register`, the event ID, and other necessary registration details.

- **Querying Information**
  - **`POST /inspect`**: Retrieve information about events and registrations. The route can be:
    - `events`: List all created events.
    - `registrations`: List all registrations.

## Code Overview

- **`index.js`**: Contains the main logic for handling event creation, registration, and querying operations.
  - **`hex2Object(hex)`**: Converts a hexadecimal string to a JavaScript object.
  - **`obj2Hex(obj)`**: Converts a JavaScript object to a hexadecimal string.
  - **`handle_advance(data)`**: Handles event creation and registration.
  - **`handle_inspect(data)`**: Provides information on events and registrations.

## Usage

1. **Create Events**

   Use the `/advance` endpoint with an action of `create_event` to create a new event. Include the event details in the payload.

2. **Register for Events**

   Use the `/advance` endpoint with an action of `register` to register for an event. Include the event ID and registration details in the payload.

3. **Query Information**

   Use the `/inspect` endpoint with the appropriate route to retrieve information about events or registrations.
---
sidebar_position: 1
title: Developer Dashboard
description: Overview of the Camino Messenger Developer Dashboard
---

# Developer Dashboard

The [Camino Messenger Developer Dashboard](https://traveltokenmarketplace.github.io/camino-messenger-contracts/) is a web interface for inspecting and managing CM Accounts and their on-chain configuration. Connect your wallet using the **Connect Wallet** button in the top right, and select your target network (e.g. Base Sepolia for testnet).

## Main Menu

### Dashboard

The landing page shows the **Network Manifest** for the selected chain: the total number of CM Accounts, the network Manager contract address, and the current Account Implementation contract address. A list of CM Accounts where your connected wallet holds a role is displayed, along with an address search to open any CM Account directly, and a **Recent Activity** panel showing the latest on-chain events.

### Activity

Displays **Ecosystem Activity** — a chronological feed of on-chain events across all CM Accounts on the selected network. Shows events from the last 10,000 blocks, with a **Load older** button to scan further back.

### Manager

Opens the management interface for a specific CM Account. See [Manager sub-sections](#manager-sub-sections) below.

### Create

A form to deploy a new CM Account. Requires an **Admin address** and an **Upgrader address**, with an optional **Initial funding** amount (in ETH) sent to the new account on creation.

---

## Manager Sub-sections

The Manager section has four tabs for managing a CM Account:

### Config

Shows the core account configuration:
- **Account Creation** — whether the account is currently active or paused (controls whether new bookings can be created).
- **Account Implementation** — the current implementation contract address used by the CM Account proxy.
- **Booking Token Address** — the BookingToken contract address associated with this account.

### Service Registry

Lists all services that must be registered before a CM Account can support or earn them. Services are grouped by category and version (e.g. Accommodation S1, Activity S1). Only registered services will be accepted by the network.

### Manager Roles

Lists the access control roles defined on the CM Account contract. Each role can be expanded to view current members and to grant or revoke the role (Admin role required for granting). The roles are:

| Role | Identifier |
|---|---|
| Admin | `DEFAULT_ADMIN_ROLE` |
| Pauser | `PAUSER_ROLE` |
| Upgrader | `UPGRADER_ROLE` |
| Versioner | `VERSIONER_ROLE` |
| Service Registry Admin | `SERVICE_REGISTRY_ADMIN_ROLE` |

### Booking Token

Shows details about the **BookingToken** contract linked to this CM Account: contract address, token name (`BookingToken`), symbol (`BToken`), and version. Also displays the current Manager address and the **Min Expiration Timestamp Diff** (the minimum time window a booking token must remain valid). Booking Token roles (Admin, Upgrader, Min Expiration Admin) are listed and manageable here.

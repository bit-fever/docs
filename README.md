# The BitFever Platform

## Introduction

**BitFever** is a platform specifically designed for algorithmic trading. The idea is to design a platform that helps
algo traders to:

- Write trading systems, using a simple IDE and leveraging a programming language specifically designed for trading
- Run them in a sandbox, taking data from a data provider and executing trades in a broker. All activities will be monitored
- Manage the portfolio, automatically selecting which systems should be activated and which ones should be deactivated

What you won't find here:
- All tools needed for a discretionary trader


## Architecture

The general architecture is described [here](architecture/architecture.md)


## Current status

The table below summarizes the development status:

| Component             | Status |
|-----------------------|--------|
| Gateway               | 100%   |
| Web user interface    | 10%    |
| Inventory Server      | 10%    |
| Portfolio Trader      | 10%    |
| Data Collector        | 0%     |
| System Adapter        | 0%     |
| Shell                 | 10%    |
| Strategy Fetcher      | 100%   |
| Keycloak integration  | 100%   |


## Roadmap

A possible roadmap is [here](roadmap.md)

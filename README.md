# Agentforce Dev Org Renewal Workflow

This repository contains a GitHub Actions workflow for automatically renewing Agentforce development organization leases to prevent expiration.

## How It Works

The workflow runs on a weekly schedule (Mondays at 8:30 PM UTC) and performs "heartbeat" operations to keep the dev org active:

1. Installs Salesforce CLI
2. Authenticates using stored SFDX URL
3. Executes test queries to maintain org activity

## Setup

1. Create a GitHub environment named `AFDevOrgRenew`
2. Add the required secret:
   - `AGENTFORCE_DEV_ORG_URL` - Your Salesforce DX auth URL

## Configuration

- **Environment**: `AFDevOrgRenew` 
- **Org alias**: `AFDevOrgRenew`
- **Schedule**: Weekly on Mondays at 8:30 PM UTC
- **Node.js version**: 20

## Manual Testing

The workflow can be triggered manually via GitHub Actions UI using the "Run workflow" button.

## Workflow File

The main workflow is located at `.github/workflows/renew.yaml`

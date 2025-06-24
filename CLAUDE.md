# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This repository contains a GitHub Actions workflow for automatically renewing Agentforce development organization leases to prevent expiration.

## Architecture

Single-purpose repository with:
- `renew.yaml` - GitHub Actions workflow that authenticates to Salesforce and performs renewal operations

## Workflow Structure

The workflow runs on a weekly schedule (Mondays at 8:30 PM UTC) and:
1. Installs Salesforce CLI
2. Authenticates using `AGENTFORCE_DEV_ORG_URL` secret
3. Executes test queries to maintain org activity

## Key Configuration

- Environment: `AFDevOrgRenew` 
- Org alias: `AFDevOrgRenew`
- Required secret: `AGENTFORCE_DEV_ORG_URL` (SFDX auth URL)
- Node.js version: 20

## Workflow Testing

Manual trigger available via GitHub Actions UI using `workflow_dispatch`.
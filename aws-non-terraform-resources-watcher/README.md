# AWS Non-Terraform Resources Watcher

## Overview

Monitors AWS CloudTrail to detect resources created or modified via Console/CLI instead of Terraform, and sends Slack reminders to responsible users.

## What It Does

- Queries CloudTrail data (via Snowflake) for human-initiated AWS changes
- Filters out Terraform, service roles, and read-only operations
- Identifies the responsible user from CloudTrail events
- Sends direct Slack messages reminding users to use Terraform

## How It Works

1. Scans CloudTrail for write operations made by human users (browser/CLI user agents)
2. Excludes Terraform-initiated changes and AWS service roles
3. Maps AWS usernames to Slack users
4. Notifies users about their non-Terraform changes

## Directory Structure

- **`datasources/`** - Snowflake and Slack connection configs
- **`knowledge/`** - CloudTrail query patterns and detection logic
- **`reports/`** - Pre-built queries for CloudTrail analysis
- **`workflows/`** - Scheduled notification workflow (runs hourly)

## Workflow

The `non-tf-notifications` workflow runs every hour (`0 * * * *`) to catch manual AWS changes and remind users to follow Infrastructure-as-Code practices.

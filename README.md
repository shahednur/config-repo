# Retail Store Configuration Repository

This repository contains centralized configuration files for the Retail Store Microservice Platform.

## Structure
- `shared/` - Common configurations across all services
- `[service-name]/` - Service-specific configurations
- `scripts/` - Utility scripts for configuration management

## Environment Profiles
- `dev` - Development environment
- `staging` - Staging environment  
- `prod` - Production environment

## Security Notes
- Sensitive properties are encrypted using `{cipher}` prefix
- Use the config server's `/encrypt` endpoint to encrypt values
- Never commit plain text passwords or secrets

## Usage
Configuration files are automatically pulled by services from the Config Server.
Services fetch their configuration based on:
- Application name
- Active profile
- Git branch/label

## Property Precedence
1. Service-specific profile configuration
2. Service-specific default configuration
3. Shared profile configuration
4. Shared default configuration

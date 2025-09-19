# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a Home Assistant Blueprint repository containing YAML automation blueprints for smart home control. Blueprints are reusable automation templates that can be imported and configured in Home Assistant.

## Repository Structure

The repository is organized into functional categories:

- **Root level**: Primary airco control blueprints (`turn_on_airco.yaml`, `turn_off_airco.yaml`)
- **`appliance-control/`**: Timer-based appliance control blueprints for managing appliance runtime and state
- **`lighting-control/`**: Lighting automation blueprints like anti-theft lighting systems

## Blueprint Architecture

Each YAML file follows Home Assistant's blueprint structure:

1. **Blueprint metadata**: Name, description, domain, and input parameters
2. **Input parameters**: Configurable entities and settings with selectors for the UI
3. **Variables**: Template variables derived from inputs
4. **Triggers**: Events that start the automation
5. **Conditions**: Logic gates that must be satisfied
6. **Actions**: Services and operations to execute

### Key Patterns

**Smart Power Management**: Airco blueprints use power surplus sensors and temperature priorities to manage multiple climate devices intelligently, preventing simultaneous operation that could overload the electrical system.

**State Coordination**: Appliance control blueprints use input_boolean entities to coordinate state between timers and device control, preventing race conditions.

**Template Logic**: Complex conditions use Jinja2 templates for comparisons, time calculations, and state evaluations.

## Development Notes

- No build, lint, or test commands - this is a pure YAML configuration repository
- Blueprints are imported directly into Home Assistant instances
- Test by importing blueprints and creating automations in Home Assistant
- YAML syntax must follow Home Assistant blueprint schema requirements
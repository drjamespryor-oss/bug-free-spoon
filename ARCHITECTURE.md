# Architecture Overview

## System Architecture Diagram

This diagram illustrates the architecture of the user data processing system, showing how user configuration flows through validation and processing layers.

```mermaid
graph TD
    A["User Input"] -->|UserConfig Interface| B["Input Validation Layer"]
    B -->|Validate Structure<br/>id, email, isActive| C{Active Status<br/>Check}
    C -->|isActive = false| D["Error Handler"]
    D -->|Throw Error| E["Error Response"]
    C -->|isActive = true| F["Process User Data"]
    F -->|Transform & Format| G["Email Normalization"]
    G -->|toLowerCase| H["Success Response"]
    H -->|Formatted String| I["Output"]
    E -->|Error Message| I
    
    style A fill:#e1f5ff
    style B fill:#f3e5f5
    style C fill:#fff3e0
    style D fill:#ffebee
    style E fill:#ffcdd2
    style F fill:#e8f5e9
    style G fill:#e0f2f1
    style H fill:#c8e6c9
    style I fill:#a5d6a7

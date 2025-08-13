# Multi-Agent-CrewAI-System

# Event Planning CrewAI System

## Project Overview
A multi-agent AI system built with CrewAI that automates and coordinates event planning tasks. The system uses three specialized agents to handle venue booking, logistics coordination, and marketing strategy for corporate events.

## Project Goal
To create an intelligent, automated event planning system that can research venues, coordinate logistics, and develop marketing strategies for technology conferences and corporate events with 200+ attendees.

## System Architecture

### Agents

#### 1. Venue Booking Specialist
- **Role**: Expert venue researcher and selector
- **Goal**: Identify, compare, and recommend 3-5 suitable venues based on capacity, location, availability, and budget constraints
- **Backstory**: Veteran venue booking specialist with extensive industry contacts and online research capabilities
- **Configuration**: 
  - `allow_delegation: false` - Works independently
  - `verbose: true` - Provides detailed output
  - `memory: true` - Remembers previous research and decisions

#### 2. Logistics Coordinator
- **Role**: Master logistics coordinator for event operations
- **Goal**: Research and secure vendors for catering, equipment, and transportation services
- **Backstory**: Experienced logistics manager with strong vendor management and budget control skills
- **Configuration**:
  - `allow_delegation: true` - Can delegate tasks to other agents
  - `verbose: true` - Provides detailed output
  - `memory: true` - Remembers vendor selections and contracts

#### 3. Marketing & Promotion Lead
- **Role**: Creative marketing strategist for event promotion
- **Goal**: Develop comprehensive marketing strategies including branding, social media campaigns, and invitation content
- **Backstory**: Creative marketer with expertise in audience engagement and campaign design
- **Configuration**:
  - `allow_delegation: false` - Works independently
  - `verbose: true` - Provides detailed output
  - `memory: true` - Remembers marketing strategies and audience insights

## Tasks

### 1. Venue Booking Task
- **Description**: Research and identify suitable venues for the event, comparing options based on capacity, location, availability, and budget constraints
- **Expected Output**: A comprehensive table listing venue name, location, capacity, price range, availability status, pros/cons, and final recommendation
- **Tools**: Serper search for online venue research
- **Guardrails**: 
  - Always verify venue information from official sources
  - Provide specific contact details and pricing when available
  - Include source URLs for all research findings
  - Cross-reference information from multiple sources
  - Verify venue availability and booking policies

### 2. Logistics Task
- **Description**: Research and secure vendors for catering, equipment, and transportation services
- **Expected Output**: A vendor matrix table with supplier name, service type, price quote, delivery time, reliability score, and contract status
- **Tools**: Serper search and web scraper for vendor research
- **Guardrails**:
  - Verify vendor credentials and reviews from multiple sources
  - Include specific pricing and contract terms when available
  - Provide backup vendor options for critical services
  - Check vendor insurance and liability coverage
  - Verify vendor availability for event dates

### 3. Marketing Task
- **Description**: Develop and execute comprehensive marketing strategy including branding, social media campaigns, and invitation content
- **Expected Output**: A marketing brief document containing campaign timeline, platforms, audience profile, sample social media posts, and finalized invitation text
- **Tools**: Serper search for industry best practices and audience research
- **Guardrails**:
  - Base marketing strategies on verified industry best practices
  - Include specific social media platform recommendations
  - Provide measurable success metrics and KPIs
  - Verify target audience demographics and preferences
  - Include budget allocation and ROI projections

## Tools Used

### 1. Serper Search Tool
- **Purpose**: Web search functionality for real-time information gathering
- **Relevance**: Essential for all agents to research current venue availability, vendor information, and industry trends
- **Usage**: Agents use this tool to find up-to-date information about venues, vendors, and marketing strategies

### 2. Web Scraper Tool
- **Purpose**: Extract specific information from websites and online sources
- **Relevance**: Particularly useful for logistics coordination to gather detailed vendor information and pricing
- **Usage**: Logistics agent uses this tool to collect comprehensive vendor data from multiple sources

## Memory and Delegation

### Memory System
- **Implementation**: All three agents have `memory: true` configuration
- **Benefits**: 
  - Agents remember previous research findings and decisions
  - Consistent decision-making across multiple interactions
  - Learning from past experiences to improve future recommendations
  - Contextual awareness of ongoing event planning process

### Delegation Strategy
- **Venue Booking Agent**: `allow_delegation: false`
  - Works independently to ensure focused venue research
  - Maintains control over venue selection process
- **Logistics Coordinator**: `allow_delegation: true`
  - Can delegate specific vendor research tasks
  - Coordinates with other agents for comprehensive logistics planning
- **Marketing Agent**: `allow_delegation: false`
  - Works independently to maintain creative control
  - Ensures consistent marketing strategy development

## Sample Output

### Venue Booking Output Example:
```
Venue Matrix:
┌─────────────────┬──────────────┬──────────┬─────────────┬──────────────┐
│ Venue Name      │ Location     │ Capacity │ Price Range │ Availability │
├─────────────────┼──────────────┼──────────┼─────────────┼──────────────┤
│ Tech Center     │ Downtown     │ 250      │ $5K-8K      │ Available    │
│ Innovation Hub  │ Midtown      │ 300      │ $6K-9K      │ Available    │
│ Conference Hall │ Business Dist│ 200      │ $4K-7K      │ Available    │
└─────────────────┴──────────────┴──────────┴─────────────┴──────────────┘

Recommendation: Tech Center - Best value for capacity and location
Source: https://techcenter.com/events
```

### Logistics Output Example:
```
Vendor Matrix:
┌──────────────┬──────────────┬──────────┬─────────────┬──────────────┐
│ Vendor Name  │ Service Type │ Price    │ Delivery   │ Reliability  │
├──────────────┼──────────────┼──────────┼─────────────┼──────────────┤
│ CaterPro     │ Catering     │ $45/person│ 2 hours   │ ⭐⭐⭐⭐⭐     │
│ EquipRent    │ AV Equipment │ $2K/day  │ Same day   │ ⭐⭐⭐⭐      │
│ TransCo      │ Transport    │ $1.5K    │ 1 hour     │ ⭐⭐⭐⭐⭐     │
└──────────────┴──────────────┴──────────┴─────────────┴──────────────┘
```

### Marketing Output Example:
```
Marketing Strategy Brief:
- Campaign Timeline: 8 weeks pre-event
- Primary Platforms: LinkedIn, Twitter, Email Marketing
- Target Audience: Tech professionals, 25-45 years old
- Key Messages: Innovation, networking, industry insights
- Success Metrics: Registration rate, social media engagement, email open rates
- Budget Allocation: 40% digital ads, 30% content creation, 30% email marketing
```

## Installation and Setup

1. Clone the repository
2. Install dependencies: `pip install crewai python-dotenv pyyaml`
3. Set up environment variables:
   - `OPENAI_API_KEY`
   - `SERPER_API_KEY`
4. Run the notebook: `jupyter notebook Usecase_crewai.ipynb`

## Usage

1. Load the notebook and run all cells
2. The system will automatically:
   - Research and recommend venues
   - Coordinate logistics and vendor selection
   - Develop comprehensive marketing strategy
3. Review outputs and adjust parameters as needed

## Features

- **Multi-Agent Collaboration**: Three specialized agents working together
- **Real-Time Research**: Uses web search and scraping for current information
- **Memory System**: Agents learn and remember from interactions
- **Guardrails**: Prevents hallucinations and ensures data accuracy
- **YAML Configuration**: Easy to modify and extend
- **Comprehensive Output**: Structured data for easy decision-making

## Future Enhancements

- Integration with booking APIs
- Real-time venue availability checking
- Automated vendor contract generation
- Social media campaign automation
- Budget tracking and optimization
- Guest list management and RSVP tracking

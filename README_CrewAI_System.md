# Event Planning CrewAI System

## 🎯 Project Goal
Multi-agent system for automated event planning using CrewAI, handling venue booking, logistics coordination, and marketing strategy. The system demonstrates advanced AI collaboration with role-playing agents, tools, memory, and guardrails.

## 🤖 Agents Description

### 1. Venue Booking Agent
- **Role**: Expert Venue Booking Specialist
- **Goal**: Research, compare, and secure ideal venues meeting capacity, location, and budget requirements
- **Backstory**: Years of experience in sourcing and booking venues for corporate and social events, with extensive network of contacts and negotiation skills
- **Memory**: Enabled for learning from previous venue searches and building knowledge over time
- **Delegation**: Restricted (false) - works independently on venue selection
- **Tools**: Web search and website scraping for venue research

### 2. Logistics Agent  
- **Role**: Master Logistics Coordinator
- **Goal**: Organize all logistical aspects including vendors, contracts, transportation, and scheduling
- **Backstory**: Backbone of successful event operations with strong background in vendor management, budget control, and deadline adherence
- **Memory**: Enabled for tracking vendor relationships, timelines, and past performance
- **Delegation**: Allowed (true) - can delegate tasks to other agents and coordinate resources
- **Tools**: Web search for vendor discovery and service comparison

### 3. Marketing Agent
- **Role**: Event Marketing & Promotion Lead  
- **Goal**: Develop comprehensive marketing strategy and campaigns to maximize attendance and engagement
- **Backstory**: Creative marketer with passion for audience engagement, excelling at crafting campaigns that spark excitement
- **Memory**: Not enabled - focuses on current campaign without historical bias
- **Delegation**: Restricted (false) - works independently on marketing strategy
- **Tools**: Web search for market trends and industry best practices

## 🛠️ Tools Used

### SerperDevTool
- **Purpose**: Web search capabilities for real-time information gathering
- **Relevance**: Enables agents to find current venue information, vendor details, and market trends
- **Usage**: Integrated into all three agent tasks for comprehensive research

### WebsiteSearchTool  
- **Purpose**: Web scraping and content extraction from specific websites
- **Relevance**: Allows agents to gather detailed information from venue websites, vendor pages, and industry resources
- **Usage**: Used by venue and logistics agents for detailed service analysis

## 🧠 Memory and Delegation Explanation

### Memory System
- **Venue & Logistics agents**: Have memory enabled to learn from previous interactions, build vendor relationships, and improve decision-making over time
- **Marketing agent**: No memory - focuses on current campaign without historical bias, ensuring fresh creative approach

### Delegation Strategy
- **Logistics agent**: Can delegate tasks to other agents (allow_delegation: true) - acts as coordinator for complex logistical operations
- **Venue & Marketing agents**: Work independently (allow_delegation: false) - maintain focus on specialized tasks without interference

## 🚧 Guardrails Implementation

### Purpose
Prevents AI hallucinations and ensures data accuracy by implementing strict validation rules for each task.

### Venue Booking Guardrails
- Always verify venue information from official sources
- Provide specific contact details and pricing when available
- Include source URLs for all research findings
- Cross-reference information from multiple sources
- Verify venue availability and booking policies

### Logistics Guardrails
- Verify vendor credentials and reviews from multiple sources
- Include specific pricing and contract terms when available
- Provide backup vendor options for critical services
- Check vendor insurance and liability coverage
- Verify vendor availability for event dates

### Marketing Guardrails
- Base marketing strategies on verified industry best practices
- Include specific social media platform recommendations
- Provide measurable success metrics and KPIs
- Verify target audience demographics and preferences
- Include budget allocation and ROI projections

## 📊 Sample Output

The system generates structured event planning data including:

### Venue Recommendations
- Venue name, location, and capacity
- Price range and availability status
- Pros/cons analysis with source verification
- Final recommendation with justification

### Vendor Matrix
- Supplier name and service type
- Price quotes and delivery time
- Reliability score and contract status
- Backup options for critical services

### Marketing Brief
- Campaign timeline and platform strategy
- Target audience profile and demographics
- Sample social media posts and content
- Budget allocation and ROI projections

## 🚀 System Architecture

### YAML Configuration
- **agents.yaml**: Defines agent roles, goals, backstories, and capabilities
- **tasks.yaml**: Specifies task descriptions, expected outputs, and guardrails
- **Modular design**: Easy to modify agent behaviors and task requirements

### Pydantic Models
- **TaskEstimate**: Structured task information with time and resource estimates
- **Milestone**: Project milestone definitions with associated tasks
- **EventPlan**: Complete event planning structure with tasks and milestones

### Crew Management
- **Sequential execution**: Tasks executed in logical order
- **Agent collaboration**: Information sharing between specialized agents
- **Result aggregation**: Structured output combining all agent contributions

## 📋 Requirements Met

✅ **3 Agents** with defined roles, goals, and backstories  
✅ **Tasks** with descriptions, expected outputs, and tools  
✅ **Tools** (SerperDev, WebsiteSearch) for external data access  
✅ **Memory** assigned to multiple agents  
✅ **Delegation** configured (true/false) for different agents  
✅ **Guardrails** implemented to prevent hallucinations  
✅ **YAML Configuration** for easy system modification  
✅ **Pydantic Models** for structured output  

## 🎉 Success Metrics

The system successfully demonstrates:
- **Agent Collaboration**: Multiple AI agents working together on complex tasks
- **Tool Integration**: External data sources enhancing AI capabilities
- **Memory Management**: Learning and improvement over time
- **Quality Control**: Guardrails ensuring accurate and reliable outputs
- **Structured Results**: Organized, actionable event planning data

## 🔧 Technical Implementation

- **Framework**: CrewAI 0.150.0
- **Language**: Python 3.x
- **Configuration**: YAML-based agent and task definitions
- **Data Validation**: Pydantic models for structured output
- **External APIs**: SerperDev for web search, WebsiteSearch for content extraction
- **Environment**: OpenAI GPT-3.5-turbo integration

---

*This system demonstrates advanced multi-agent AI collaboration for real-world event planning applications, showcasing the power of specialized AI agents working together with proper tools, memory, and quality controls.*

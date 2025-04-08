# EverSure Business Process Management Project
## Merging Traditional and Digital Insurance Processes

**Team Members:**
- Vibhu
- Arnav
- Archie
- Isha
- Richa
- Sahaj

**Course:** BUS 353: Business Process Management

**Date:** April 1, 2025

## Table of Contents

1. Introduction
2. As-Is Process Models
   - Traditional Process
   - Digital Process
3. As-Is Process Analysis
   - Cycle Time Efficiency Calculations
   - Issue Register
4. Process Redesign
   - Proposed Changes
   - Expected Benefits
5. Conclusion
6. References

## 1. Introduction

EverSure has been providing insurance to businesses for more than 20 years. With their deep understanding of customers and ability to offer the "right" products, they have experienced increasing revenues over the past 10 years. However, with the emergence of many new digital companies, they have found it harder to acquire new customers. As part of their strategy, EverSure acquired a digital competitor.

This report analyzes the current traditional and digital processes at EverSure, identifies key issues, and proposes a set of changes to merge these processes into a single, more efficient process. The goal is to leverage the strengths of both approaches while addressing their respective weaknesses to create a unified process that improves overall business performance.

## 2. As-Is Process Models

### Traditional Process

The traditional sales process at EverSure begins with sales representatives identifying potential customers and submitting requests to sales admin for customer reports. After receiving reports, sales representatives book meetings with potential clients, with a 90% success rate. Following meetings, interested clients (60%) receive offers prepared by sales admin and modified by sales representatives. Customers may accept (50%), decline (35%), or request modifications (15%). Accepted contracts are processed by back office in the CNTR and OPER systems, followed by payment processing with a 5% error rate.

[BPMN model for traditional process to be inserted here]

### Digital Process

The digital process begins with the marketing team generating leads through earned (white papers, case studies) and paid (Google ads) methods. An algorithm filters out 50% of leads as irrelevant before assigning the remainder to sales representatives. Sales reviews web form data and selects standard offers in a highly standardized process (10 minutes per case). Customers may accept (15%), decline, request contact, or not respond (70% after 3 weeks). Accepted offers are automatically sent to back office for processing in the INSU system, followed by data entry into the AUIN system with a 15% error rate.

[BPMN model for digital process to be inserted here]

## 3. As-Is Process Analysis

### Cycle Time Efficiency Calculations

Cycle time efficiency is calculated as the ratio of value-added time (processing time) to the total cycle time (processing time + waiting time).

**Traditional Process:**
- Total Processing Time: 21 hours (best case)
- Total Waiting Time: 216 hours (best case)
- Total Cycle Time: 237 hours
- Cycle Time Efficiency: 21 / 237 = 8.86%

With offer modifications and payment errors:
- Total Processing Time: 24 hours
- Total Waiting Time: 312 hours
- Total Cycle Time: 336 hours
- Cycle Time Efficiency: 24 / 336 = 7.14%

**Digital Process:**
- Total Processing Time: 10.27 hours (best case)
- Total Waiting Time: 152 hours (best case)
- Total Cycle Time: 162.27 hours
- Cycle Time Efficiency: 10.27 / 162.27 = 6.33%

With contact request:
- Total Processing Time: 14.27 hours
- Total Waiting Time: 168 hours
- Total Cycle Time: 182.27 hours
- Cycle Time Efficiency: 14.27 / 182.27 = 7.83%

**Assumptions:**
- Working week of 40 hours
- Sequential process flow (no parallel activities)
- For activities without specified waiting times, waiting time is assumed to be 0
- For activities with specified total time but unspecified processing time, reasonable estimates are made

### Issue Register

**Issue 1: Inefficient Information Systems Integration**

EverSure operates with multiple disconnected information systems across the traditional and digital business units. The traditional business uses CNTR and OPER systems, while the digital business uses INSU and AUIN systems. This lack of integration creates redundant data entry, increases error rates, and prevents information sharing between business units.

Evidence:
- Traditional process uses CNTR for contract registration and OPER for customer data management
- Digital process uses INSU for initial data entry and AUIN for customer data management
- AUIN system performs the same functions as OPER but with a higher error rate (15% vs. 5%)
- No indication of data sharing between traditional and digital processes

Impact:
- Higher error rates in digital process (15% vs. 5% in traditional)
- Duplicate customer information across systems
- Increased training requirements for staff
- Missed cross-selling opportunities
- Higher overall IT costs

**Issue 2: Excessive Waiting Times in Traditional Process**

The traditional sales process suffers from significant waiting times at multiple stages, particularly in customer report preparation (1 week waiting) and the period between report receipt and client meeting (2 weeks total time with only 3 hours of processing). These delays extend the overall cycle time and reduce efficiency.

Evidence:
- Customer report preparation: 4 hours processing time but 1 week waiting time
- Client meeting scheduling and preparation: 3 hours processing time but 2 weeks total time
- Offer preparation and approval: 5 hours processing time but 3 days total time
- Cycle time efficiency calculation shows traditional process at only ~8.5% efficiency

Impact:
- Extended sales cycle reduces competitiveness
- Potential customers may find alternative solutions during waiting periods
- Sales representatives handle fewer leads per month (100 visits vs. 1000 leads in digital)
- Opportunity cost of missed potential customers (estimated 20% improvement potential)

**Issue 3: High Rate of "Bad" Leads in Digital Process**

The digital process suffers from inefficient lead qualification, with 50% of leads filtered out by the algorithm and only 10% of the remaining leads that receive offers converting to contracts. Additionally, 70% of leads never respond, resulting in significant wasted effort and resources.

Evidence:
- 50% of initial leads are filtered out by the algorithm
- 70% of leads that receive offers never respond (considered "dead" after 3 weeks)
- Only 10% of leads that receive offers convert to contracts
- Company believes they could improve the ratio of "good" leads by 20%

Impact:
- Significant wasted effort in lead generation and offer preparation
- Low return on marketing investment
- Sales representatives' time spent on non-converting leads
- Reduced overall profitability of digital business

## 4. Process Redesign

### Proposed Changes

**Change 1: Unified Information System Implementation**

What will be added or dropped:
- Added: A single, integrated information system that combines the functionality of CNTR, OPER, INSU, and AUIN
- Dropped: Separate systems and redundant data entry

What will be done differently:
- Customer data will be entered once and accessible across all departments
- Contract information will be stored in a centralized database
- Lead information from both channels will be integrated
- Automated data validation will be implemented to reduce errors

Issues addressed:
- Issue 1: Inefficient Information Systems Integration

Performance measures improved:
- Error rates will decrease from 15% to 5% or lower in the digital process
- Back office processing time will be reduced by 10% as specified in merger benefits
- IT costs will be reduced by 20,000€ annually as specified in merger benefits
- Cross-selling opportunities will increase through better visibility of customer data

Related BPR principles/redesign heuristics:
- Technology enablement: Using IT to eliminate routine manual activities
- Integration: Connecting processes that were previously fragmented
- Standardization: Creating uniform procedures and systems
- Error prevention: Designing systems to prevent errors rather than fixing them afterward

**Change 2: Hybrid Lead Generation and Qualification Process**

What will be added or dropped:
- Added: Advanced lead scoring algorithm that incorporates traditional sales expertise
- Added: Pre-qualification step before offer preparation for all leads
- Dropped: Separate lead generation processes for traditional and digital channels

What will be done differently:
- Digital marketing team will generate leads for both channels
- Algorithm will be enhanced with criteria from traditional sales expertise
- Leads will be scored and categorized based on potential value and conversion likelihood
- High-value leads will be directed to traditional sales process
- Standard leads will be directed to digital sales process

Issues addressed:
- Issue 3: High Rate of "Bad" Leads in Digital Process

Performance measures improved:
- Ratio of "good" leads will improve by 20% as specified in improvement potential
- Conversion rate of digital leads will increase from 10% to at least 15%
- Non-response rate will decrease from 70% to below 50%
- More efficient resource allocation between high-value and standard leads

Related BPR principles/redesign heuristics:
- Task elimination: Removing unnecessary effort on poor-quality leads
- Task composition: Combining related tasks into a composite task
- Triage: Directing different types of cases to appropriate resources
- Empower: Giving workers more decision-making authority in the process

**Change 3: Streamlined Customer Report and Offer Preparation**

What will be added or dropped:
- Added: Automated report generation using the unified information system
- Added: Standardized offer templates for different customer segments
- Dropped: Manual preparation of customer reports by sales admin
- Dropped: Separate offer preparation processes for traditional and digital

What will be done differently:
- Customer reports will be generated automatically using predefined templates
- Sales representatives will have direct access to report generation
- Standard offers will be automatically suggested based on customer data
- Sales representatives can customize standard offers for high-value clients

Issues addressed:
- Issue 2: Excessive Waiting Times in Traditional Process

Performance measures improved:
- Customer report preparation waiting time will be reduced from 1 week to near-zero
- Offer preparation processing time will be reduced from 5 hours to 1-2 hours
- Cycle time efficiency will improve from 8.5% to at least 15% for traditional process
- Traditional business can target 20% more customers as specified in improvement potential

Related BPR principles/redesign heuristics:
- Automation: Using technology to perform tasks
- Case manager: Making a single person responsible for the entire case
- Resequencing: Changing the order of tasks
- Parallelism: Performing tasks in parallel rather than sequentially

**Change 4: Integrated Contract and Payment Processing**

What will be added or dropped:
- Added: Unified contract processing workflow for both channels
- Added: Automated payment tracking and reconciliation
- Dropped: Separate back office processes for traditional and digital contracts

What will be done differently:
- A single back office team will handle all contracts regardless of origin
- Contract templates will be standardized but customizable
- Customer data verification will be partially automated
- Payment tracking will be integrated with the unified information system

Issues addressed:
- Issue 1: Inefficient Information Systems Integration
- Issue 2: Excessive Waiting Times in Traditional Process

Performance measures improved:
- Back office processing time will be reduced by 10% as specified in merger benefits
- Error rates in contract processing will decrease to 5% or lower
- Payment investigation time will be reduced through better tracking
- Staff utilization will improve through workload balancing

Related BPR principles/redesign heuristics:
- Case-based work: Organizing the work based on cases rather than functions
- Integration: Connecting processes that were previously fragmented
- Exception handling: Separating normal cases from exceptions
- Control relocation: Moving controls into the process

### Expected Benefits

1. **Efficiency Improvements**
   - Reduced waiting times throughout the process
   - Improved cycle time efficiency from under 10% to at least 15%
   - 10% reduction in back office processing time
   - 30% reduction in customer data validation time

2. **Cost Savings**
   - 20,000€ annual IT cost savings from unified system
   - Reduced training and maintenance costs
   - More efficient resource allocation
   - Lower error rates and rework

3. **Business Growth**
   - 20% increase in customer reach for traditional business
   - 20% improvement in ratio of "good" leads for digital business
   - Increased cross-selling opportunities
   - Higher conversion rates across both channels

4. **Customer Experience**
   - Faster response times
   - More consistent service across channels
   - Personalized offers based on comprehensive customer data
   - Fewer errors in contract processing

## 5. Conclusion

The analysis of EverSure's traditional and digital processes has revealed significant opportunities for improvement through process merger. The traditional process offers deep customer understanding and high-value contracts but suffers from excessive waiting times and inefficiency. The digital process provides speed and volume but struggles with lead quality and higher error rates.

By implementing the proposed changes—unified information system, hybrid lead generation, streamlined report and offer preparation, and integrated contract processing—EverSure can create a merged process that leverages the strengths of both approaches while addressing their respective weaknesses.

The expected benefits include improved efficiency, cost savings, business growth, and enhanced customer experience. These improvements align with EverSure's strategic goals of maintaining their competitive edge in an increasingly digital market while leveraging their traditional strengths in customer understanding and relationship management.

## 6. References

- EverSure case study documentation
- BUS 353 course materials on Business Process Management
- BPMN modeling guidelines

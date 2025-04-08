# Traditional Process BPMN Model Instructions

## Overview
This document provides guidance for creating the BPMN model for EverSure's traditional insurance sales process. The model should capture all activities, actors, decision points, and information flows described in the case study.

## Key Participants (Pools/Lanes)
1. **EverSure Traditional**
   - Sales Representative
   - Sales Admin
   - Back Office

2. **Customer** (separate pool)

## Process Flow

### Initial Lead Generation and Qualification
1. Sales Representative identifies potential customers (2 hours)
2. Sales Representative submits request to Sales Admin
3. Sales Admin prepares customer report using CNTR system (4 hours processing, 1 week waiting)
4. Sales Admin sends report back to Sales Representative

### Client Meeting Process
1. Sales Representative books meeting with potential client (90% success rate)
2. Sales Representative prepares for and conducts meeting (3 hours processing, 2 weeks total time)
3. Decision point based on meeting outcome:
   - Interested (60%)
   - Not interested (30%)
   - Has existing contract (10%)

### Offer Preparation and Response
1. For interested clients:
   - Sales Representative sends data to Sales Admin
   - Sales Admin prepares offer (4 hours)
   - Sales Representative modifies and approves offer (1 hour)
   - Sales Representative sends offer to customer
2. For clients with existing contracts:
   - Sales Admin makes note for future contact
3. Customer response (decision point):
   - Accept (50%)
   - Decline (35%)
   - Accept with modifications (15%)
4. For modifications:
   - Loop back to modify offer until accepted

### Contract Processing
1. Back Office registers contract in CNTR system
2. Back Office registers customer data in OPER system
3. Back Office archives contract
4. Total processing time: 3 hours (no waiting time)

### Payment Processing
1. Back Office generates daily reports of expected payments
2. Back Office extracts bank account payment reports
3. Back Office reconciles payments
4. Decision point:
   - Payment OK
   - Payment missing (requires investigation)
5. For missing payments:
   - Investigation process (1 additional hour + 2 days waiting)

## BPMN Elements to Include
- Start and end events
- Tasks with appropriate icons (manual, service, etc.)
- Gateways (exclusive, parallel, inclusive as needed)
- Sequence flows with conditions
- Message flows between pools
- Data objects (reports, offers, contracts)
- Time annotations for processing and waiting times

## Modeling Tips
1. Use separate pools for EverSure and Customer
2. Use lanes within EverSure pool to distinguish between roles
3. Include data objects to show information flow
4. Annotate with time information
5. Use appropriate gateway types for decision points
6. Include probabilities on decision paths where provided

## Tool Instructions
Use the free web-based BPMN tool: https://demo.bpmn.io/new
- Save the model in .bpmn format
- Ensure all elements are properly labeled
- Follow course modeling guidelines

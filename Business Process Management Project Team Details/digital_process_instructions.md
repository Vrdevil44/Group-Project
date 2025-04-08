# Digital Process BPMN Model Instructions

## Overview
This document provides guidance for creating the BPMN model for EverSure's digital insurance sales process. The model should capture all activities, actors, decision points, and information flows described in the case study.

## Key Participants (Pools/Lanes)
1. **EverSure Digital**
   - Digital Marketing Team
   - Sales Representative
   - Back Office

2. **Customer** (separate pool)

## Process Flow

### Lead Generation and Processing
1. Digital Marketing Team generates leads (6 hours)
   - Earned leads (white reports, case studies, guest blogs)
   - Paid leads (Google ads)
2. Algorithm filters irrelevant leads (50% filtered out)
   - Students downloading white papers
   - Spam emails
3. Algorithm assigns relevant leads to Sales Representatives

### Offer Preparation and Response
1. Sales Representative reviews web form data
2. Sales Representative selects best standard offer (10 minutes per case)
3. Sales Representative sends offer to potential customer
4. Customer response (decision point):
   - Accept (15%)
   - Decline
   - Wish to be contacted
   - No response (reminder sent automatically)
5. If no response after 3 weeks, lead considered dead (70% of cases)

### Contact Request Handling
1. For customers who wish to be contacted:
   - Sales Representative contacts customer
   - Sales Representative modifies standard contract
   - Customer accepts offer (100% conversion)
   - Processing time: 4 hours
   - Waiting time: 2 days

### Accepted Offer Processing
1. Offer and customer acceptance automatically sent to digital Back Office
2. Back Office enters data into INSU system
3. Back Office verifies customer data:
   - Checks customer and contract data
   - Contacts customer for bank account information
4. Back Office generates contract and sends to customer
   - Processing time: 3 hours per client
   - Waiting time: 4 days
5. Back Office enters data into AUIN system
6. Error handling (15% error rate):
   - Investigation and correction process

## BPMN Elements to Include
- Start and end events
- Tasks with appropriate icons (manual, service, user, etc.)
- Gateways (exclusive, parallel, inclusive as needed)
- Sequence flows with conditions
- Message flows between pools
- Data objects (leads, offers, contracts)
- Time annotations for processing and waiting times

## Modeling Tips
1. Use separate pools for EverSure Digital and Customer
2. Use lanes within EverSure Digital pool to distinguish between roles
3. Include data objects to show information flow
4. Annotate with time information
5. Use appropriate gateway types for decision points
6. Include probabilities on decision paths where provided
7. Show automated processes with appropriate task types

## Tool Instructions
Use the free web-based BPMN tool: https://demo.bpmn.io/new
- Save the model in .bpmn format
- Ensure all elements are properly labeled
- Follow course modeling guidelines

# BPMN Model Template - Digital Process

Below is a textual representation of how the BPMN model for the digital process should be structured. Use this as a guide when creating the actual model in bpmn.io.

## Pools and Lanes

### Pool: EverSure Digital
- Lane: Digital Marketing Team
- Lane: Sales Representative
- Lane: Back Office

### Pool: Customer

## Process Flow Elements

### Lane: Digital Marketing Team
1. Start Event: "Start Lead Generation"
2. Task (Manual): "Generate earned leads" (white reports, case studies, guest blogs)
3. Task (Manual): "Generate paid leads" (Google ads)
4. Task (Service): "Filter leads with algorithm"
5. Gateway (Exclusive): "Lead relevant?"
   - Path: "No (50%)" → End Event: "Lead filtered out"
   - Path: "Yes (50%)" → "Assign lead to Sales Representative"
6. Task (Service): "Assign lead to Sales Representative"

### Lane: Sales Representative
1. Task (Receive): "Receive assigned lead"
2. Task (User): "Review web form data"
3. Task (User): "Select best standard offer" (10 minutes)
4. Task (Send): "Send offer to potential customer"
5. Task (Service): "Set reminder timer"
6. Gateway (Event-Based): "Customer response?"
   - Path: "Accept (15%)" → "Forward to Back Office"
   - Path: "Decline" → End Event: "Offer declined"
   - Path: "Wish to be contacted" → "Contact customer"
   - Path: "No response after 3 weeks (70%)" → End Event: "Lead considered dead"
7. Task (Manual): "Contact customer" (4 hours)
8. Task (Manual): "Modify standard contract"
9. Task (Send): "Send modified offer to customer"
10. Task (Receive): "Receive acceptance" (100% conversion)
11. Task (Send): "Forward to Back Office"

### Lane: Back Office
1. Task (Receive): "Receive accepted offer"
2. Task (Service): "Enter data into INSU system"
3. Task (Manual): "Verify customer data" (part of 3 hours)
4. Task (Manual): "Contact customer for bank information" (part of 3 hours)
5. Gateway (Exclusive): "Data verification complete?"
   - Path: "No" → "Verify customer data" (loop)
   - Path: "Yes" → "Generate contract"
6. Task (Service): "Generate contract" (part of 3 hours)
7. Task (Send): "Send contract to customer"
8. Task (Manual): "Enter data into AUIN system"
9. Gateway (Exclusive): "Errors in data entry?"
   - Path: "Yes (15%)" → "Investigate and correct errors"
   - Path: "No (85%)" → End Event: "Process complete"
10. Task (Manual): "Investigate and correct errors"
11. End Event: "Process complete"
12. Data Store: "INSU System"
13. Data Store: "AUIN System"

### Pool: Customer
1. Task (Receive): "Receive offer"
2. Gateway (Exclusive): "Response decision?"
   - Path: "Accept" → "Send acceptance"
   - Path: "Decline" → "Send decline"
   - Path: "Need modifications" → "Request contact"
   - Path: "Ignore" → End Event: "No response"
3. Task (Send): "Send acceptance"
4. Task (Send): "Send decline"
5. Task (Send): "Request contact"
6. Task (Receive): "Receive modified offer"
7. Task (Send): "Accept modified offer"
8. Task (Receive): "Receive contract"
9. Task (Send): "Provide bank information"

## Message Flows
- Sales Representative → Customer: Offer
- Customer → Sales Representative: Acceptance/Decline/Contact request
- Sales Representative → Customer: Modified offer (if applicable)
- Customer → Sales Representative: Modified offer acceptance
- Back Office → Customer: Contract request
- Customer → Back Office: Bank information
- Back Office → Customer: Final contract

## Data Objects
- "Lead data"
- "Web form data"
- "Standard offer"
- "Modified offer"
- "Customer verification data"
- "Bank information"
- "Contract document"

## Time Annotations
- Add time annotations to relevant activities:
  - Lead generation: 6 hours
  - Offer selection and sending: 10 minutes
  - Customer response waiting: 3 weeks maximum
  - Customer contact and modification: 4 hours (2 days waiting)
  - Data verification and contract generation: 3 hours (4 days waiting)
  - Error investigation: Additional time based on complexity

# BPMN Model Template - Traditional Process

Below is a textual representation of how the BPMN model for the traditional process should be structured. Use this as a guide when creating the actual model in bpmn.io.

## Pools and Lanes

### Pool: EverSure Traditional
- Lane: Sales Representative
- Lane: Sales Admin
- Lane: Back Office

### Pool: Customer

## Process Flow Elements

### Lane: Sales Representative
1. Start Event: "Start Lead Generation"
2. Task (Manual): "Identify potential new customers" (2 hours)
3. Task (Send): "Submit request to Sales Admin"
4. Task (Receive): "Receive customer report"
5. Task (Manual): "Book meeting with potential client"
6. Gateway (Exclusive): "Client agrees to meeting?"
   - Path: "Yes (90%)" → "Prepare for meeting"
   - Path: "No (10%)" → End Event: "Lead declined"
7. Task (Manual): "Prepare for meeting" (part of 3 hours)
8. Task (Manual): "Conduct client meeting" (part of 3 hours)
9. Gateway (Exclusive): "Meeting outcome?"
   - Path: "Interested (60%)" → "Send data to Sales Admin for offer"
   - Path: "Not interested (30%)" → End Event: "Lead declined"
   - Path: "Has existing contract (10%)" → "Notify Sales Admin about future contact"
10. Task (Send): "Send data to Sales Admin for offer"
11. Task (Receive): "Receive prepared offer"
12. Task (Manual): "Modify and approve offer" (1 hour)
13. Task (Send): "Send offer to customer"
14. Task (Receive): "Receive customer response"
15. Gateway (Exclusive): "Customer response?"
    - Path: "Accept (50%)" → "Forward to Back Office"
    - Path: "Decline (35%)" → End Event: "Offer declined"
    - Path: "Accept with modifications (15%)" → "Modify offer based on feedback"
16. Task (Manual): "Modify offer based on feedback"
17. Task (Send): "Send modified offer to customer" (loops back to "Receive customer response")
18. Task (Send): "Forward to Back Office"

### Lane: Sales Admin
1. Task (Receive): "Receive request from Sales"
2. Task (Manual): "Prepare customer report using CNTR" (4 hours)
3. Task (Send): "Send report to Sales Representative"
4. Task (Receive): "Receive data for offer preparation"
5. Task (Manual): "Prepare offer" (4 hours)
6. Task (Send): "Send offer to Sales Representative"
7. Task (Receive): "Receive notification about future contact"
8. Task (Manual): "Make note for future contact"
9. Data Store: "CNTR System"

### Lane: Back Office
1. Task (Receive): "Receive accepted contract"
2. Task (Manual): "Register contract in CNTR" (part of 3 hours)
3. Task (Manual): "Register customer data in OPER" (part of 3 hours)
4. Task (Manual): "Archive contract" (part of 3 hours)
5. Task (Manual): "Generate daily payment reports" (part of 4 hours)
6. Task (Manual): "Extract bank account payment reports" (part of 4 hours)
7. Task (Manual): "Reconcile payments" (part of 4 hours)
8. Gateway (Exclusive): "Payment status?"
   - Path: "OK" → End Event: "Process complete"
   - Path: "Missing (5%)" → "Investigate payment issue"
9. Task (Manual): "Investigate payment issue" (1 additional hour)
10. End Event: "Process complete"
11. Data Store: "OPER System"

### Pool: Customer
1. Task (Receive): "Receive meeting request"
2. Task (Send): "Respond to meeting request"
3. Task (Receive): "Participate in meeting"
4. Task (Receive): "Receive offer"
5. Task (Send): "Respond to offer"
6. Task (Receive): "Receive modified offer" (if applicable)
7. Task (Send): "Respond to modified offer" (if applicable)
8. Task (Receive): "Receive contract"

## Message Flows
- Sales Representative → Customer: Meeting request
- Customer → Sales Representative: Meeting response
- Sales Representative → Customer: Offer
- Customer → Sales Representative: Offer response
- Sales Representative → Customer: Modified offer (if applicable)
- Customer → Sales Representative: Modified offer response (if applicable)
- Back Office → Customer: Contract

## Data Objects
- "Customer identification data"
- "Customer report"
- "Meeting notes"
- "Offer data"
- "Offer document"
- "Modified offer document"
- "Contract document"
- "Payment records"

## Time Annotations
- Add time annotations to relevant activities:
  - Customer identification: 2 hours
  - Report preparation: 4 hours (1 week waiting)
  - Meeting preparation and conduct: 3 hours (2 weeks total)
  - Offer preparation: 4 hours (Sales Admin), 1 hour (Sales)
  - Offer response: 2 weeks average
  - Contract processing: 3 hours
  - Payment processing: 4 hours
  - Payment investigation: 1 additional hour (2 days waiting)

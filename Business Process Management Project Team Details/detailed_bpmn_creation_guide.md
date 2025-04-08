# Detailed Line-by-Line BPMN Model Creation Guide

## Introduction

This guide provides detailed, step-by-step instructions for creating the BPMN models for EverSure's traditional and digital processes using the bpmn.io web-based tool. Follow these instructions precisely to create compliant BPMN diagrams that meet all project requirements.

## Accessing the Tool

1. Open your web browser and navigate to https://demo.bpmn.io/new
2. You will see a blank canvas with a palette of BPMN elements on the left side
3. Save your work frequently using File > Save Diagram (select .bpmn format)

## Traditional Process BPMN Model - Step by Step

### Step 1: Set Up Pools and Lanes
1. Drag a "Pool" from the palette to the canvas
2. Click on the pool and type "EverSure Traditional" as the name
3. Click on the wrench icon that appears when you select the pool
4. Add three lanes by clicking "+" in the lane configuration menu
5. Name the lanes from top to bottom:
   - "Sales Representative"
   - "Sales Admin"
   - "Back Office"
6. Drag another "Pool" below the first one
7. Name this pool "Customer"

### Step 2: Add Start Event and Initial Activities in Sales Representative Lane
1. Click on the "Sales Representative" lane to select it
2. Drag a "Start Event" to the left side of this lane
3. Name it "Start Lead Generation"
4. Drag a "Task" element to the right of the start event
5. Name it "Identify potential new customers"
6. Add a text annotation connected to this task: "2 hours"
7. Drag a "Send Task" to the right of the previous task
8. Name it "Submit request to Sales Admin"
9. Draw a sequence flow connecting these elements in order

### Step 3: Add Activities in Sales Admin Lane (First Part)
1. Click on the "Sales Admin" lane to select it
2. Drag a "Receive Task" to align with the "Submit request" task above
3. Name it "Receive request from Sales"
4. Drag a "Task" element to the right of the receive task
5. Name it "Prepare customer report using CNTR"
6. Add a text annotation: "4 hours, 1 week waiting"
7. Drag a "Send Task" to the right of the previous task
8. Name it "Send report to Sales Representative"
9. Draw sequence flows connecting these elements in order
10. Drag a "Data Store" to the bottom of the Sales Admin lane
11. Name it "CNTR System"
12. Add an association from "Prepare customer report" to this data store

### Step 4: Continue Sales Representative Activities
1. Return to the "Sales Representative" lane
2. Drag a "Receive Task" to align with the "Send report" task below
3. Name it "Receive customer report"
4. Drag a "Task" element to the right
5. Name it "Book meeting with potential client"
6. Drag an "Exclusive Gateway" (diamond with X) to the right
7. Name it "Client agrees to meeting?"
8. Draw sequence flows connecting these elements
9. From the gateway, draw two sequence flows:
   - One going right to a new "Task" (name it "Prepare for meeting")
   - One going down to an "End Event" (name it "Lead declined")
10. Label the first sequence flow "Yes (90%)"
11. Label the second sequence flow "No (10%)"
12. Add a text annotation to "Prepare for meeting": "part of 3 hours"
13. Drag another "Task" to the right of "Prepare for meeting"
14. Name it "Conduct client meeting"
15. Add a text annotation: "part of 3 hours"
16. Connect these with sequence flows

### Step 5: Add Decision Point After Meeting
1. Drag an "Exclusive Gateway" to the right of "Conduct client meeting"
2. Name it "Meeting outcome?"
3. Draw three sequence flows from this gateway:
   - One going right to a new "Send Task" (name it "Send data to Sales Admin for offer")
   - One going down to an "End Event" (name it "Lead declined")
   - One going down and right to a new "Task" (name it "Notify Sales Admin about future contact")
4. Label these sequence flows:
   - "Interested (60%)"
   - "Not interested (30%)"
   - "Has existing contract (10%)"
5. Connect "Notify Sales Admin about future contact" to an End Event

### Step 6: Continue Sales Representative and Sales Admin Interaction
1. In the "Sales Admin" lane, add a "Receive Task" aligned with "Send data to Sales Admin"
2. Name it "Receive data for offer preparation"
3. Add a "Task" to the right
4. Name it "Prepare offer"
5. Add a text annotation: "4 hours"
6. Add a "Send Task" to the right
7. Name it "Send offer to Sales Representative"
8. Connect these with sequence flows
9. In the "Sales Representative" lane, add a "Receive Task" aligned with "Send offer"
10. Name it "Receive prepared offer"
11. Add a "Task" to the right
12. Name it "Modify and approve offer"
13. Add a text annotation: "1 hour"
14. Add a "Send Task" to the right
15. Name it "Send offer to customer"
16. Connect these with sequence flows

### Step 7: Add Customer Response Handling
1. Add a "Receive Task" to the right of "Send offer to customer"
2. Name it "Receive customer response"
3. Add an "Exclusive Gateway" to the right
4. Name it "Customer response?"
5. Draw three sequence flows from this gateway:
   - One going right to a new "Send Task" (name it "Forward to Back Office")
   - One going down to an "End Event" (name it "Offer declined")
   - One going down and right to a new "Task" (name it "Modify offer based on feedback")
6. Label these sequence flows:
   - "Accept (50%)"
   - "Decline (35%)"
   - "Accept with modifications (15%)"
7. From "Modify offer based on feedback", add a "Send Task"
8. Name it "Send modified offer to customer"
9. Draw a sequence flow from this task back to "Receive customer response" to create a loop
10. Add a text annotation to this section: "2 weeks average"

### Step 8: Add Back Office Activities
1. In the "Back Office" lane, add a "Receive Task" aligned with "Forward to Back Office"
2. Name it "Receive accepted contract"
3. Add a "Task" to the right
4. Name it "Register contract in CNTR"
5. Add a text annotation: "part of 3 hours"
6. Add a "Task" to the right
7. Name it "Register customer data in OPER"
8. Add a text annotation: "part of 3 hours"
9. Add a "Task" to the right
10. Name it "Archive contract"
11. Add a text annotation: "part of 3 hours"
12. Connect these with sequence flows
13. Add a "Data Store" below these tasks
14. Name it "OPER System"
15. Add associations from "Register customer data in OPER" to this data store

### Step 9: Add Payment Processing in Back Office
1. Add a "Task" to the right of "Archive contract"
2. Name it "Generate daily payment reports"
3. Add a "Task" to the right
4. Name it "Extract bank account payment reports"
5. Add a "Task" to the right
6. Name it "Reconcile payments"
7. Add a text annotation to this section: "4 hours total"
8. Add an "Exclusive Gateway" to the right
9. Name it "Payment status?"
10. Draw two sequence flows from this gateway:
    - One going right to an "End Event" (name it "Process complete")
    - One going down and right to a new "Task" (name it "Investigate payment issue")
11. Label these sequence flows:
    - "OK (95%)"
    - "Missing (5%)"
12. From "Investigate payment issue", draw a sequence flow to an "End Event"
13. Add a text annotation to "Investigate payment issue": "1 additional hour, 2 days waiting"

### Step 10: Add Customer Activities
1. In the "Customer" pool, add activities that interact with EverSure:
2. Add a "Receive Task" aligned with "Book meeting with potential client"
3. Name it "Receive meeting request"
4. Add a "Send Task" to the right
5. Name it "Respond to meeting request"
6. Add a "Task" aligned with "Conduct client meeting"
7. Name it "Participate in meeting"
8. Add a "Receive Task" aligned with "Send offer to customer"
9. Name it "Receive offer"
10. Add a "Send Task" to the right
11. Name it "Respond to offer"
12. Add a "Receive Task" aligned with "Send modified offer to customer"
13. Name it "Receive modified offer"
14. Add a "Send Task" to the right
15. Name it "Respond to modified offer"
16. Add a "Receive Task" aligned with the Back Office section
17. Name it "Receive contract"
18. Connect these with sequence flows within the Customer pool

### Step 11: Add Message Flows Between Pools
1. Add message flows (dashed lines with open arrowheads) between corresponding activities:
2. From "Submit request to Sales Admin" to "Receive request from Sales"
3. From "Send report to Sales Representative" to "Receive customer report"
4. From "Book meeting with potential client" to "Receive meeting request"
5. From "Respond to meeting request" to before "Prepare for meeting"
6. From "Send data to Sales Admin for offer" to "Receive data for offer preparation"
7. From "Send offer to Sales Representative" to "Receive prepared offer"
8. From "Send offer to customer" to "Receive offer"
9. From "Respond to offer" to "Receive customer response"
10. From "Send modified offer to customer" to "Receive modified offer"
11. From "Respond to modified offer" to "Receive customer response"
12. From "Register contract in CNTR" to "Receive contract"

### Step 12: Add Data Objects
1. Add data objects to represent information flowing through the process:
2. Add a "Data Object" near "Identify potential new customers"
3. Name it "Customer identification data"
4. Add a "Data Object" near "Prepare customer report using CNTR"
5. Name it "Customer report"
6. Add a "Data Object" near "Conduct client meeting"
7. Name it "Meeting notes"
8. Add a "Data Object" near "Prepare offer"
9. Name it "Offer data"
10. Add a "Data Object" near "Send offer to customer"
11. Name it "Offer document"
12. Add a "Data Object" near "Send modified offer to customer"
13. Name it "Modified offer document"
14. Add a "Data Object" near "Register contract in CNTR"
15. Name it "Contract document"
16. Add a "Data Object" near "Reconcile payments"
17. Name it "Payment records"
18. Connect these data objects to relevant activities using associations

## Digital Process BPMN Model - Step by Step

### Step 1: Set Up Pools and Lanes
1. Create a new diagram in bpmn.io
2. Drag a "Pool" from the palette to the canvas
3. Click on the pool and type "EverSure Digital" as the name
4. Click on the wrench icon that appears when you select the pool
5. Add three lanes by clicking "+" in the lane configuration menu
6. Name the lanes from top to bottom:
   - "Digital Marketing Team"
   - "Sales Representative"
   - "Back Office"
7. Drag another "Pool" below the first one
8. Name this pool "Customer"

### Step 2: Add Digital Marketing Team Activities
1. Click on the "Digital Marketing Team" lane to select it
2. Drag a "Start Event" to the left side of this lane
3. Name it "Start Lead Generation"
4. Drag a "Task" element to the right of the start event
5. Name it "Generate earned leads"
6. Add a text annotation: "white reports, case studies, guest blogs"
7. Drag another "Task" element below and slightly to the right
8. Name it "Generate paid leads"
9. Add a text annotation: "Google ads"
10. Add a text annotation connected to both tasks: "6 hours total"
11. Drag a "Service Task" (task with gear icon) to the right
12. Name it "Filter leads with algorithm"
13. Drag an "Exclusive Gateway" to the right
14. Name it "Lead relevant?"
15. Draw sequence flows connecting these elements appropriately
16. From the gateway, draw two sequence flows:
    - One going right to a new "Service Task" (name it "Assign lead to Sales Representative")
    - One going down to an "End Event" (name it "Lead filtered out")
17. Label the first sequence flow "Yes (50%)"
18. Label the second sequence flow "No (50%)"

### Step 3: Add Sales Representative Activities
1. Click on the "Sales Representative" lane to select it
2. Drag a "Receive Task" aligned with "Assign lead to Sales Representative"
3. Name it "Receive assigned lead"
4. Drag a "User Task" (task with person icon) to the right
5. Name it "Review web form data"
6. Drag another "User Task" to the right
7. Name it "Select best standard offer"
8. Add a text annotation: "10 minutes"
9. Drag a "Send Task" to the right
10. Name it "Send offer to potential customer"
11. Drag a "Service Task" to the right
12. Name it "Set reminder timer"
13. Connect these with sequence flows

### Step 4: Add Customer Response Handling
1. Drag an "Event-Based Gateway" (circle within diamond) to the right of "Set reminder timer"
2. Name it "Customer response?"
3. Draw four sequence flows from this gateway:
   - One going right to a new "Send Task" (name it "Forward to Back Office")
   - One going down to an "End Event" (name it "Offer declined")
   - One going down and right to a new "Task" (name it "Contact customer")
   - One going up and right to an "End Event" (name it "Lead considered dead")
4. Label these sequence flows:
   - "Accept (15%)"
   - "Decline"
   - "Wish to be contacted"
   - "No response after 3 weeks (70%)"
5. Add a text annotation to this section: "3 weeks maximum waiting time"

### Step 5: Add Contact Request Handling
1. From "Contact customer", add a "Task" to the right
2. Name it "Modify standard contract"
3. Add a text annotation to these tasks: "4 hours, 2 days waiting"
4. Add a "Send Task" to the right
5. Name it "Send modified offer to customer"
6. Add a "Receive Task" to the right
7. Name it "Receive acceptance"
8. Add a text annotation: "100% conversion"
9. Add a "Send Task" to the right
10. Name it "Forward to Back Office"
11. Connect these with sequence flows

### Step 6: Add Back Office Activities
1. In the "Back Office" lane, add a "Receive Task" aligned with both "Forward to Back Office" paths
2. Name it "Receive accepted offer"
3. Add a "Service Task" to the right
4. Name it "Enter data into INSU system"
5. Add a "Task" to the right
6. Name it "Verify customer data"
7. Add a "Task" below and to the right
8. Name it "Contact customer for bank information"
9. Add a text annotation to these tasks: "3 hours total, 4 days waiting"
10. Add a "Data Store" below
11. Name it "INSU System"
12. Add an association from "Enter data into INSU system" to this data store

### Step 7: Add Contract Generation and Data Entry
1. Add an "Exclusive Gateway" to the right of the verification tasks
2. Name it "Data verification complete?"
3. Draw two sequence flows from this gateway:
   - One going back to "Verify customer data" (create a loop)
   - One going right to a new "Service Task" (name it "Generate contract")
4. Label these sequence flows:
   - "No"
   - "Yes"
5. Add a "Send Task" to the right of "Generate contract"
6. Name it "Send contract to customer"
7. Add a "Task" to the right
8. Name it "Enter data into AUIN system"
9. Add a "Data Store" below
10. Name it "AUIN System"
11. Add an association from "Enter data into AUIN system" to this data store

### Step 8: Add Error Handling
1. Add an "Exclusive Gateway" to the right of "Enter data into AUIN system"
2. Name it "Errors in data entry?"
3. Draw two sequence flows from this gateway:
   - One going right to an "End Event" (name it "Process complete")
   - One going down and right to a new "Task" (name it "Investigate and correct errors")
4. Label these sequence flows:
   - "No (85%)"
   - "Yes (15%)"
5. From "Investigate and correct errors", draw a sequence flow back to "Enter data into AUIN system"

### Step 9: Add Customer Activities
1. In the "Customer" pool, add activities that interact with EverSure Digital:
2. Add a "Receive Task" aligned with "Send offer to potential customer"
3. Name it "Receive offer"
4. Add an "Exclusive Gateway" to the right
5. Name it "Response decision?"
6. Draw four sequence flows from this gateway to:
   - A "Send Task" (name it "Send acceptance")
   - A "Send Task" (name it "Send decline")
   - A "Send Task" (name it "Request contact")
   - An "End Event" (name it "No response")
7. Label these appropriately
8. Add a "Receive Task" aligned with "Send modified offer to customer"
9. Name it "Receive modified offer"
10. Add a "Send Task" to the right
11. Name it "Accept modified offer"
12. Add a "Receive Task" aligned with "Send contract to customer"
13. Name it "Receive contract"
14. Add a "Send Task" aligned with "Contact customer for bank information"
15. Name it "Provide bank information"
16. Connect these with appropriate sequence flows within the Customer pool

### Step 10: Add Message Flows Between Pools
1. Add message flows (dashed lines with open arrowheads) between corresponding activities:
2. From "Send offer to potential customer" to "Receive offer"
3. From "Send acceptance" to the path leading to "Forward to Back Office"
4. From "Send decline" to the path leading to "Offer declined"
5. From "Request contact" to the path leading to "Contact customer"
6. From "Send modified offer to customer" to "Receive modified offer"
7. From "Accept modified offer" to "Receive acceptance"
8. From "Contact customer for bank information" to "Provide bank information"
9. From "Provide bank information" to after "Contact customer for bank information"
10. From "Send contract to customer" to "Receive contract"

### Step 11: Add Data Objects
1. Add data objects to represent information flowing through the process:
2. Add a "Data Object" near "Generate earned leads"
3. Name it "Lead data"
4. Add a "Data Object" near "Review web form data"
5. Name it "Web form data"
6. Add a "Data Object" near "Select best standard offer"
7. Name it "Standard offer"
8. Add a "Data Object" near "Modify standard contract"
9. Name it "Modified offer"
10. Add a "Data Object" near "Verify customer data"
11. Name it "Customer verification data"
12. Add a "Data Object" near "Contact customer for bank information"
13. Name it "Bank information"
14. Add a "Data Object" near "Generate contract"
15. Name it "Contract document"
16. Connect these data objects to relevant activities using associations

## Final Steps for Both Models

### Step 1: Review and Validate
1. Check that all activities are properly connected with sequence flows
2. Verify that all message flows between pools are correctly aligned
3. Ensure all gateways have appropriate outgoing paths with labels
4. Confirm that all data objects and data stores are connected to relevant activities
5. Verify that all time annotations are included

### Step 2: Format and Organize
1. Align elements horizontally and vertically for a clean layout
2. Ensure consistent spacing between elements
3. Adjust the size of pools and lanes if needed
4. Make sure all labels are visible and not overlapping

### Step 3: Save in Required Format
1. Click "File" > "Save Diagram"
2. Select .bpmn format
3. Name the files appropriately:
   - "EverSure_Traditional_Process.bpmn"
   - "EverSure_Digital_Process.bpmn"
4. Download both files to your computer

### Step 4: Verify Requirements Compliance
1. Confirm both models include:
   - Proper pools and lanes
   - Start and end events
   - Appropriate task types
   - Exclusive gateways for decisions
   - Message flows between pools
   - Data objects and data stores
   - Time annotations
   - Probability labels on decision paths

By following these detailed instructions, you will create comprehensive BPMN models that accurately represent EverSure's traditional and digital processes and meet all project requirements.

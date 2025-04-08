# BPMN Modeling Guide for bpmn.io

## Accessing the Tool
1. Go to https://demo.bpmn.io/new
2. You'll see a blank canvas with a palette of BPMN elements on the left side

## Basic BPMN Elements

### Events
- **Start Event**: Circle with thin border - marks the beginning of a process
- **End Event**: Circle with thick border - marks the end of a process
- **Intermediate Event**: Double-bordered circle - represents something that happens during the process

### Activities
- **Task**: Rounded rectangle - represents a single unit of work
- **Sub-Process**: Rounded rectangle with a small "+" sign - contains a set of activities

### Gateways
- **Exclusive Gateway (XOR)**: Diamond with "X" - represents a decision point where only one path is taken
- **Parallel Gateway (AND)**: Diamond with "+" - splits flow into multiple parallel paths
- **Inclusive Gateway (OR)**: Diamond with "O" - represents a decision point where one or more paths can be taken

### Connecting Objects
- **Sequence Flow**: Solid line with arrowhead - shows the order of activities
- **Message Flow**: Dashed line with open arrowhead - shows messages between participants
- **Association**: Dotted line - links artifacts to elements

### Swimlanes
- **Pool**: Container for a process participant (e.g., EverSure, Customer)
- **Lane**: Sub-division within a pool (e.g., Sales Rep, Back Office)

### Artifacts
- **Data Object**: Document icon - represents information used or produced
- **Text Annotation**: Allows adding notes to the diagram

## Step-by-Step Instructions

### 1. Set Up Pools and Lanes
1. Drag a "Pool" from the palette to the canvas
2. Name the pool (e.g., "EverSure Traditional")
3. Add lanes by clicking on the pool and using the wrench icon
4. Name each lane (e.g., "Sales Representative", "Sales Admin", "Back Office")
5. Add a separate pool for "Customer"

### 2. Add Start and End Events
1. Drag a "Start Event" to the beginning of your process
2. Drag "End Event(s)" to the appropriate ending points

### 3. Add Activities
1. Drag "Task" elements to represent each activity
2. Name each task descriptively (e.g., "Identify potential customers")
3. Use appropriate task types:
   - User Task: Human performs the task with system support
   - Manual Task: Human performs the task without system
   - Service Task: Automated system task
   - Send/Receive Task: Sending/receiving messages

### 4. Add Gateways
1. Drag appropriate gateway types for decision points
2. Label each gateway with a question (e.g., "Customer interested?")
3. Label outgoing sequence flows with answers (e.g., "Yes", "No")

### 5. Connect Elements
1. Use Sequence Flows to connect elements within the same pool
2. Use Message Flows to connect elements between different pools
3. Ensure proper flow direction (generally left to right)

### 6. Add Data Objects and Annotations
1. Drag Data Objects to represent important information
2. Connect them to relevant activities with Associations
3. Add Text Annotations to provide additional information

### 7. Save Your Work
1. Click "File" > "Save Diagram"
2. Choose .bpmn format
3. Download the file to your computer

## Tips for Creating Clear BPMN Models

1. **Maintain Consistent Flow Direction**: Generally left-to-right, top-to-bottom
2. **Use Descriptive Labels**: Clear, concise names for all elements
3. **Limit Gateway Complexity**: Avoid too many paths from a single gateway
4. **Group Related Activities**: Consider sub-processes for complex sections
5. **Include Time Information**: Add annotations for processing/waiting times
6. **Show Probabilities**: Add annotations for decision probabilities
7. **Validate Your Model**: Check for disconnected elements or improper connections
8. **Balance Detail Level**: Include enough detail to understand the process without overwhelming

## Common Mistakes to Avoid

1. Mixing up sequence flows and message flows
2. Forgetting to label gateways and paths
3. Creating "spaghetti diagrams" with crossing lines
4. Using incorrect gateway types
5. Omitting important decision points
6. Inconsistent level of detail across the model
7. Missing start or end events
8. Improper pool/lane usage

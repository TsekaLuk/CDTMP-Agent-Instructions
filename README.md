# Cognitive Decision and Task Management Protocol (CDTMP)

中文 | [English](README_zh.md)

![License](https://img.shields.io/github/license/tsekaluk/CDTMP-Agent-Instructions)

---

## Introduction

The **Cognitive Decision and Task Management Protocol (CDTMP)** is an innovative method designed to address the challenges of maintaining contextual continuity in high-complexity tasks among intelligent agents. Based on Anthropic's research on building effective agents through simple, composable patterns [1] and findings on the impact of prompt formatting on LLM performance [2], CDTMP offers a comprehensive, professional, engineering-based, and reusable solution. Leveraging advanced prompt engineering techniques, CDTMP ensures that contextual information is consistently and accurately preserved and transmitted throughout the collaborative task execution process.

---

## Features

- **Contextual Continuity Maintenance**: Maintains consistency and continuity of task context in complex tasks through sophisticated task decomposition and tracking.
- **Engineering-Based Design**: Provides a structured and modular solution based on system engineering principles, with comprehensive task analysis and management.
- **Reusability**: Applicable to various intelligent agents and task types, reducing development costs through standardized protocols.
- **Innovative Prompt Engineering**: Optimizes information transmission and understanding between agents using advanced NLP techniques.
- **High Adaptability**: Addresses challenges of agents' lack of mutual awareness and rapid context forgetting, maintaining collaboration efficiency.
- **Task Analysis & Decomposition**: Implements sophisticated algorithms for breaking down complex tasks into manageable subtasks.
- **Progress Tracking**: Maintains detailed progress records with emoji-based status indicators and comprehensive metadata.
- **Performance Optimization**: Includes built-in performance metrics and bottleneck identification.

## Architecture

The CDTMP system consists of several key components:

### 1. Task Analysis Engine

- Unique task ID generation
- Task priority determination
- Project architecture design
- Code logic optimization
- Algorithm selection and optimization
- Module division
- Naming convention management

### 2. Structured Documentation System

- Dynamic notepad creation
- Structured file naming
- Task metadata recording
- Progress tracking
- Performance metrics

### 3. Execution Framework

- Subtask execution management
- Error handling and retry mechanisms
- Concurrent execution capabilities
- Integration with development tools
- Real-time status updates

### 4. Feedback & Optimization

- User feedback collection
- Performance analysis
- Continuous improvement mechanisms
- Knowledge transfer systems

---

## Main Implementation Details

The following pseudocode demonstrates the core implementation of the CDTMP system:

```python
// Pseudocode for Building an Effective Intelligent Agent

// Constants and Configurations
DEFINE ANTHROPIC_THINKING_PROTOCOL
DEFINE CURSOR_TOOLS_CREATE_FILE_FUNCTION
DEFINE NOTEPAD_FORMAT = "markdown"
DEFINE COUPLING_THRESHOLD = 5
DEFINE EMOJI_MAPPING = {
    COMPLETED: "✅",
    IN_PROGRESS: "🔄",
    FAILED: "❌",
    NEEDS_ATTENTION: "⚠️",
    HIGH_PRIORITY: "🚀"
}
DEFINE MAX_RETRIES = 3

// Enumerations for Task Status
ENUM TaskStatus {
    NOT_COMPLETED,
    COMPLETED,
    NOT_DECOMPOSED,
    DECOMPOSED,
    NOT_PLANNED,
    PLANNED,
    IMPOSSIBLE,
    PRIORITY_HIGH,
    PRIORITY_MEDIUM,
    PRIORITY_LOW,
    IN_PROGRESS,
    NEEDS_ATTENTION,
    FAILED
}

// Data Structures
STRUCT Task {
    id: STRING // Using UUID for uniqueness
    name: STRING
    status: TaskStatus
    priority: TaskStatus
    dependencies: LIST<STRING> // List of Task IDs
    summary: STRING
    subTasks: LIST<Task>
    toolExecutionMethod: STRING
    filePath: STRING
    contextIdea: STRING
    userIntent: STRING
    taskConstraints: STRING
    userEmphasis: STRING
    failureCases: STRING
    coupledFiles: STRING
    futureConcerns: STRING
    innovativeTasks: STRING
    estimatedEffort: INTEGER // in hours
    actualEffort: INTEGER // in hours
    assignedPersonnel: STRING
    deadline: DATE
    retries: INTEGER // Number of retry attempts
}

STRUCT Notepad {
    filePath: STRING
    tasks: LIST<Task>
    performanceMetrics: DICTIONARY<STRING, FLOAT>
    bottlenecks: LIST<STRING>
    recommendations: LIST<STRING>
    knowledgeTransfer: STRING
}

// Helper Functions

// Function to Generate Unique Task ID
FUNCTION generateUniqueTaskID() -> STRING:
    // Implement a robust UUID generation mechanism
    RETURN UUID_GENERATOR() // Assume a UUID generator is available
END FUNCTION

// Function to Extract Main Task Name from User Input using NLP
FUNCTION extractMainTaskName(taskInput: STRING) -> STRING:
    // Implement NLP to accurately extract main task name
    // Example: Use an NLP library to identify key phrases
    extractedName = NLP_ExtractMainTaskName(taskInput) // Placeholder for NLP extraction
    IF extractedName IS EMPTY:
        extractedName = "Unnamed Task"
    END IF
    RETURN extractedName
END FUNCTION

// Function to Determine Task Priority Based on Input
FUNCTION determinePriority(taskInput: STRING) -> TaskStatus:
    // Analyze taskInput to determine priority (HIGH, MEDIUM, LOW)
    IF containsUrgentKeywords(taskInput):
        RETURN TaskStatus.PRIORITY_HIGH
    ELSE IF containsModerateKeywords(taskInput):
        RETURN TaskStatus.PRIORITY_MEDIUM
    ELSE:
        RETURN TaskStatus.PRIORITY_LOW
    END IF
END FUNCTION

// Function to Check for Urgent Keywords
FUNCTION containsUrgentKeywords(text: STRING) -> BOOLEAN:
    urgentKeywords = ["urgent", "immediately", "asap", "critical"]
    FOR EACH keyword IN urgentKeywords:
        IF LOWERCASE(text) CONTAINS LOWERCASE(keyword):
            RETURN TRUE
        END IF
    END FOR
    RETURN FALSE
END FUNCTION

// Function to Check for Moderate Keywords
FUNCTION containsModerateKeywords(text: STRING) -> BOOLEAN:
    moderateKeywords = ["soon", "priority", "important"]
    FOR EACH keyword IN moderateKeywords:
        IF LOWERCASE(text) CONTAINS LOWERCASE(keyword):
            RETURN TRUE
        END IF
    END FOR
    RETURN FALSE
END FUNCTION

// Function to Design Project Architecture
FUNCTION designProjectArchitecture(task: Task):
    // Design a modular and scalable project architecture
    // Example: Define modules like UI, Backend, Database, etc.
    task.summary += "Designed modular architecture with the following components: UI, Backend, Database.\n"
END FUNCTION

// Function to Optimize Code Logic
FUNCTION optimizeCodeLogic(task: Task):
    // Define clear and efficient code logic
    // Example: Implement design patterns, optimize algorithms
    task.summary += "Optimized code logic using MVC pattern and optimized sorting algorithm for better performance.\n"
END FUNCTION

// Function to Select and Optimize Algorithms
FUNCTION selectAndOptimizeAlgorithms(task: Task):
    // Choose suitable algorithms and optimize them
    // Example: Selecting QuickSort over BubbleSort for efficiency
    task.summary += "Selected QuickSort algorithm for sorting tasks and optimized it for large datasets.\n"
END FUNCTION

// Function to Divide Task into Modules
FUNCTION divideIntoModules(task: Task) -> LIST<Task>:
    // Divide the main task into independent modules
    subTasks = LIST<Task>()

    // Example Subtasks based on task name
    IF task.name CONTAINS "UI":
        subTask1 = new Task()
        subTask1.id = generateUniqueTaskID()
        subTask1.name = "Design UI Components"
        subTask1.status = TaskStatus.NOT_PLANNED
        subTask1.priority = task.priority
        subTask1.estimatedEffort = 20
        subTask1.assignedPersonnel = "UI Team"
        subTask1.deadline = ADD_DAYS(CURRENT_DATE, 10)
        subTask1.retries = 0
        subTasks.ADD(subTask1)
    END IF

    IF task.name CONTAINS "Backend":
        subTask2 = new Task()
        subTask2.id = generateUniqueTaskID()
        subTask2.name = "Develop Backend APIs"
        subTask2.status = TaskStatus.NOT_PLANNED
        subTask2.priority = task.priority
        subTask2.estimatedEffort = 30
        subTask2.assignedPersonnel = "Backend Team"
        subTask2.deadline = ADD_DAYS(CURRENT_DATE, 15)
        subTask2.retries = 0
        subTasks.ADD(subTask2)
    END IF

    IF task.name CONTAINS "Database":
        subTask3 = new Task()
        subTask3.id = generateUniqueTaskID()
        subTask3.name = "Set Up Database"
        subTask3.status = TaskStatus.NOT_PLANNED
        subTask3.priority = task.priority
        subTask3.estimatedEffort = 25
        subTask3.assignedPersonnel = "Database Team"
        subTask3.deadline = ADD_DAYS(CURRENT_DATE, 12)
        subTask3.retries = 0
        subTasks.ADD(subTask3)
    END IF

    // Add more conditional subtask creation based on task specifics

    RETURN subTasks
END FUNCTION

// Function to Define Naming Conventions for Variables and Classes
FUNCTION defineNamingConventions(task: Task):
    // Define descriptive naming conventions
    // Example: camelCase for variables, PascalCase for classes
    task.summary += "Adopted camelCase for variable names and PascalCase for class names to enhance readability.\n"
END FUNCTION

// Function to Decompose Main Task into Subtasks
FUNCTION decomposeIntoSubTasks(task: Task) -> LIST<Task>:
    // Implement detailed decomposition logic
    RETURN divideIntoModules(task)
END FUNCTION

// Function to Create Structured Notepad File
FUNCTION createNotepad(mainTask: Task) -> Notepad:
    // Step 2: Create Structured Notepad File

    // Determine Notepad File Location based on Coupling and Complexity
    notepadLocation = determineNotepadLocation(mainTask)

    // Define Notepad File Name using Structured Naming Method
    notepadName = generateNotepadName(mainTask)

    // Create Notepad File using Cursor Tools
    notepadPath = CURSOR_TOOLS_CREATE_FILE_FUNCTION(notepadLocation, notepadName, NOTEPAD_FORMAT)

    // Initialize Notepad Structure
    notepad = new Notepad()
    notepad.filePath = notepadPath
    notepad.tasks = mainTask.subTasks
    notepad.performanceMetrics = DICTIONARY<STRING, FLOAT>()
    notepad.bottlenecks = LIST<STRING>()
    notepad.recommendations = LIST<STRING>()
    notepad.knowledgeTransfer = ""

    // Record Task Metadata in Notepad
    FOR EACH subTask IN notepad.tasks:
        recordTaskMetadata(notepad, subTask)
    END FOR

    RETURN notepad
END FUNCTION

// Function to Determine Notepad File Location
FUNCTION determineNotepadLocation(task: Task) -> STRING:
    // Logic to determine the appropriate directory for the notepad
    // Example: If high coupling, place in main directory; else, in specific module directory
    IF countCoupledFiles(task.coupledFiles) > COUPLING_THRESHOLD:
        RETURN "/project/main/"
    ELSE:
        RETURN "/project/modules/"
    END IF
END FUNCTION

// Function to Count Coupled Files
FUNCTION countCoupledFiles(coupledFiles: STRING) -> INTEGER:
    // Count the number of coupled files based on the string (assuming comma-separated)
    IF coupledFiles IS EMPTY:
        RETURN 0
    END IF
    RETURN LENGTH(SPLIT(coupledFiles, ","))
END FUNCTION

// Function to Generate Structured Notepad File Name
FUNCTION generateNotepadName(task: Task) -> STRING:
    // Structured naming without timestamps, reflecting task metadata
    // Example: "UI_Design_Notepad_High.md", "Backend_API_Planning_Medium.md"
    moduleName = extractModuleName(task.name)
    priority = extractPriorityString(task.priority)
    RETURN moduleName + "_Planning_" + priority + ".md"
END FUNCTION

// Function to Extract Module Name from Task Name
FUNCTION extractModuleName(taskName: STRING) -> STRING:
    // Extract module name based on task name (e.g., "Design UI Components" -> "UI_Design")
    words = SPLIT(taskName, " ")
    IF LENGTH(words) >= 3:
        RETURN words[2] + "_" + words[0] // Assuming "Design UI Components" -> "UI_Design"
    ELSE IF LENGTH(words) == 2:
        RETURN words[1] + "_" + words[0]
    ELSE:
        RETURN words[0] + "_Task"
    END IF
END FUNCTION

// Function to Extract Priority String from TaskStatus
FUNCTION extractPriorityString(priority: TaskStatus) -> STRING:
    IF priority == TaskStatus.PRIORITY_HIGH:
        RETURN "High"
    ELSE IF priority == TaskStatus.PRIORITY_MEDIUM:
        RETURN "Medium"
    ELSE:
        RETURN "Low"
    END IF
END FUNCTION

// Function to Record Task Metadata in Notepad
FUNCTION recordTaskMetadata(notepad: Notepad, task: Task):
    // Record the initial metadata of each sub-task in the notepad
    metadataLine = "- [ ] " + task.name + " " + EMOJI_MAPPING[TaskStatus.NOT_COMPLETED] + 
                  " (Status: " + task.status.toString() + 
                  ", Priority: " + task.priority.toString() + ")"
    APPEND(metadataLine, notepad.filePath)
END FUNCTION

// Function to Update Notepad Upon Task Completion
FUNCTION updateNotepad(notepad: Notepad, completedTask: Task):
    // Step 3: Update Notepad Upon Task Completion

    // Mark Task as Completed with Emoji
    markTaskAsCompleted(notepad, completedTask)

    // Generate and Append Task Summary
    summary = generateTaskSummary(completedTask)
    appendSummaryToNotepad(notepad, completedTask, summary)

    // Update Performance Metrics, Bottlenecks, Recommendations if applicable
    updatePerformanceMetrics(notepad, completedTask)
    identifyBottlenecks(notepad, completedTask)
    provideRecommendations(notepad, completedTask)
    transferKnowledge(notepad, completedTask)
END FUNCTION

// Function to Mark Task as Completed with Emoji
FUNCTION markTaskAsCompleted(notepad: Notepad, task: Task):
    // Use Emoji to mark the task as completed
    // Example: Replace "- [ ] Task Name ❌" with "- [✅] Task Name ✅"
    originalLine = "- [ ] " + task.name + " " + EMOJI_MAPPING[TaskStatus.NOT_COMPLETED]
    completedLine = "- [✅] " + task.name + " " + EMOJI_MAPPING[TaskStatus.COMPLETED]
    REPLACE(originalLine, completedLine, notepad.filePath)
END FUNCTION

// Function to Generate Task Summary
FUNCTION generateTaskSummary(task: Task) -> STRING:
    // Generate a detailed summary for the completed task
    summary = "### Summary of " + task.name + "\n"
    summary += "- **Tool Execution Method**: " + task.toolExecutionMethod + "\n"
    summary += "- **Relative Path of Operated File Objects**: " + task.filePath + "\n"
    summary += "- **Main Context Ideas**: " + task.contextIdea + "\n"
    summary += "- **User's Potential Requirements**: " + task.userIntent + "\n"
    summary += "- **Easily Overlooked or Misunderstood Task Constraints**: " + task.taskConstraints + "\n"
    summary += "- **Key Points Repeatedly Emphasized by User**: " + task.userEmphasis + "\n"
    summary += "- **Summary of Failed Cases in Task**: " + task.failureCases + "\n"
    summary += "- **Coupled Code Files and Key Functions**: " + task.coupledFiles + "\n"
    summary += "- **Future Concerns and Development Experience**: " + task.futureConcerns + "\n"
    summary += "- **Extensible Innovative Thinking Tasks**: " + task.innovativeTasks + "\n"

    // Additional Contextual Information
    summary += "- **Contextual Information**: Detailed context based on task history and interactions.\n"

    // Error Reporting
    IF task.failureCases IS NOT EMPTY:
        summary += "- **Error Reports**: " + task.failureCases + "\n"
    END IF

    RETURN summary
END FUNCTION

// Function to Append Task Summary to Notepad
FUNCTION appendSummaryToNotepad(notepad: Notepad, task: Task, summary: STRING):
    // Append the summary under the respective task in the notepad
    // Locate the task in the notepad and append the summary
    lineNumber = locateTaskLine(notepad.filePath, task.name)
    IF lineNumber != -1:
        INSERT(summary, lineNumber + 1, notepad.filePath)
    ELSE:
        APPEND(summary, notepad.filePath)
    END IF
END FUNCTION

// Function to Locate Task Line in Notepad
FUNCTION locateTaskLine(filePath: STRING, taskName: STRING) -> INTEGER:
    // Return the line number where the task is located
    lineNumber = 0
    FOR EACH line IN READ_LINES(filePath):
        lineNumber += 1
        IF line CONTAINS taskName:
            RETURN lineNumber
        END IF
    END FOR
    RETURN -1 // Not found
END FUNCTION

// Function to Update Performance Metrics
FUNCTION updatePerformanceMetrics(notepad: Notepad, task: Task):
    // Example: Track actual effort vs. estimated effort
    metricName = "Effort_" + task.id
    IF task.estimatedEffort > 0:
        performance = task.actualEffort / task.estimatedEffort
    ELSE:
        performance = 0
    END IF
    notepad.performanceMetrics[metricName] = performance
END FUNCTION

// Function to Identify Bottlenecks
FUNCTION identifyBottlenecks(notepad: Notepad, task: Task):
    // Example: Identify tasks that took longer than estimated
    IF task.actualEffort > task.estimatedEffort:
        bottleneck = "Task " + task.name + " exceeded estimated effort."
        notepad.bottlenecks.ADD(bottleneck)
    END IF
END FUNCTION

// Function to Provide Recommendations
FUNCTION provideRecommendations(notepad: Notepad, task: Task):
    // Example: Suggest optimizations based on performance
    IF task.actualEffort > task.estimatedEffort:
        recommendation = "Review and optimize the " + task.name + " process to better estimate and reduce effort."
        notepad.recommendations.ADD(recommendation)
    END IF
END FUNCTION

// Function to Transfer Knowledge
FUNCTION transferKnowledge(notepad: Notepad, task: Task):
    // Example: Summarize lessons learned
    knowledge = "Learned to better estimate effort for " + task.name + ". Consider potential obstacles in future tasks."
    notepad.knowledgeTransfer += knowledge + "\n"
END FUNCTION

// Function to Summarize Main Task Completion
FUNCTION summarizeMainTask(notepad: Notepad, mainTask: Task):
    // Step 4: Summarize Main Task Completion

    // Mark the main task as completed
    summaryLine = "√ Task Completed " + EMOJI_MAPPING[TaskStatus.COMPLETED]
    APPEND(summaryLine, notepad.filePath)

    // Write the main task summary
    mainSummary = "### 主任务总结\n"
    mainSummary += "- **自身限制**: " + mainTask.summaryLimitations + "\n"
    mainSummary += "- **整体任务回顾**: " + mainTask.summaryOverview + "\n"
    mainSummary += "- **结构化指导**: " + mainTask.summaryGuidance + "\n"
    mainSummary += "- **绩效指标**: " + FORMAT_METRICS(notepad.performanceMetrics) + "\n"
    mainSummary += "- **瓶颈识别**: " + JOIN_LIST(notepad.bottlenecks, ", ") + "\n"
    mainSummary += "- **建议与改进**: " + JOIN_LIST(notepad.recommendations, ", ") + "\n"
    mainSummary += "- **知识转移**: " + notepad.knowledgeTransfer + "\n"

    APPEND(mainSummary, notepad.filePath)
END FUNCTION

// Function to Format Performance Metrics
FUNCTION FORMAT_METRICS(metrics: DICTIONARY<STRING, FLOAT>) -> STRING:
    formatted = ""
    FOR EACH key, value IN metrics:
        formatted += key + ": " + FLOAT_TO_STRING(value) + "\n"
    END FOR
    RETURN formatted
END FUNCTION

// Function to Join List into String
FUNCTION JOIN_LIST(items: LIST<STRING>, separator: STRING) -> STRING:
    joinedString = ""
    FOR EACH item IN items:
        IF joinedString != "":
            joinedString += separator + " "
        END IF
        joinedString += item
    END FOR
    RETURN joinedString
END FUNCTION

// Function to Handle Incomplete Main Task
FUNCTION handleIncompleteMainTask(notepad: Notepad, mainTask: Task):
    // Step 5: Further Decompose Incomplete Main Task

    IF mainTask has incomplete subTasks:
        FOR EACH incompleteSubTask IN mainTask.subTasks:
            IF isTaskComplex(incompleteSubTask):
                furtherSubTasks = decomposeIntoSubTasks(incompleteSubTask)
                incompleteSubTask.subTasks = furtherSubTasks
                incompleteSubTask.status = TaskStatus.DECOMPOSED
                appendFurtherSubTasksToNotepad(notepad, incompleteSubTask, furtherSubTasks)
                handleIncompleteMainTask(notepad, incompleteSubTask)
            END IF
        END FOR
    END IF
END FUNCTION

// Function to Check if a Task is Complex
FUNCTION isTaskComplex(task: Task) -> BOOLEAN:
    // Define complexity criteria (e.g., number of dependencies, estimated effort)
    IF countCoupledFiles(task.coupledFiles) > COUPLING_THRESHOLD OR 
       LENGTH(task.dependencies) > COUPLING_THRESHOLD:
        RETURN TRUE
    ELSE:
        RETURN FALSE
    END IF
END FUNCTION

// Function to Append Further Subtasks to Notepad
FUNCTION appendFurtherSubTasksToNotepad(notepad: Notepad, parentTask: Task, subTasks: LIST<Task>):
    // Create entries for further subtasks in the notepad
    FOR EACH subTask IN subTasks:
        recordTaskMetadata(notepad, subTask)
    END FOR
END FUNCTION

// Function to Execute a Subtask
FUNCTION executeSubTask(task: Task):
    // Implement task execution logic here
    TRY:
        IF task.name CONTAINS "Design UI":
            designUIComponents()
        ELSE IF task.name CONTAINS "Develop Backend":
            developBackendAPIs()
        ELSE IF task.name CONTAINS "Set Up Database":
            setUpDatabase()
        // Add more task execution cases as needed
        task.actualEffort = CALCULATE_EFFORT(task.id) // Placeholder for effort tracking
    CATCH Exception e:
        task.status = TaskStatus.FAILED
        task.failureCases = e.message
        logError(e)
        notifyStakeholders(e)
    END TRY
END FUNCTION

// Example Implementations for Subtask Execution
FUNCTION designUIComponents():
    // Implement UI design logic
    // Example: Create UI mockups, code UI components
    // Update task details as necessary
    // Placeholder implementation
END FUNCTION

FUNCTION developBackendAPIs():
    // Implement Backend API development logic
    // Example: Develop RESTful APIs, integrate with database
    // Update task details as necessary
    // Placeholder implementation
END FUNCTION

FUNCTION setUpDatabase():
    // Implement Database setup logic
    // Example: Design database schema, configure database server
    // Update task details as necessary
    // Placeholder implementation
END FUNCTION

// Function to Execute a Task and Update Status
FUNCTION executeAndUpdate(task: Task, notepad: Notepad):
    // Execute the task
    executeSubTask(task)

    // Update task status based on execution outcome
    IF task.status != TaskStatus.FAILED:
        task.status = TaskStatus.COMPLETED
    ELSE:
        // Handle failed task (could retry or escalate)
        IF shouldRetry(task):
            retryTask(task, notepad)
        ELSE:
            escalateTask(task, notepad)
        END IF
    END IF

    // Update the notepad with task completion or failure
    updateNotepad(notepad, task)
END FUNCTION

// Function to Determine if a Failed Task Should be Retried
FUNCTION shouldRetry(task: Task) -> BOOLEAN:
    // Define retry logic based on task type or error
    IF task.retries < MAX_RETRIES:
        RETURN TRUE
    ELSE:
        RETURN FALSE
    END IF
END FUNCTION

// Function to Retry a Failed Task
FUNCTION retryTask(task: Task, notepad: Notepad):
    // Increment retry count and attempt to re-execute
    task.retries += 1
    executeAndUpdate(task, notepad)
END FUNCTION

// Function to Escalate a Failed Task
FUNCTION escalateTask(task: Task, notepad: Notepad):
    // Notify stakeholders or take alternative actions
    notification = "Task " + task.name + " has failed after maximum retries."
    SEND_NOTIFICATION(notification)
    // Optionally, mark as needs attention
    task.status = TaskStatus.NEEDS_ATTENTION
    markTaskAsNeedsAttention(notepad, task)
END FUNCTION

// Function to Mark Task as Needs Attention
FUNCTION markTaskAsNeedsAttention(notepad: Notepad, task: Task):
    // Use Emoji to mark the task as needing attention
    originalLine = "- [ ] " + task.name + " " + EMOJI_MAPPING[TaskStatus.NOT_COMPLETED]
    attentionLine = "- [⚠️] " + task.name + " " + EMOJI_MAPPING[TaskStatus.NEEDS_ATTENTION]
    REPLACE(originalLine, attentionLine, notepad.filePath)
END FUNCTION

// Function to Log Errors
FUNCTION logError(e: Exception):
    // Implement logging mechanism
    LOG("Error: " + e.message)
END FUNCTION

// Function to Notify Stakeholders
FUNCTION notifyStakeholders(message: STRING):
    // Implement notification mechanism (e.g., email, Slack)
    SEND_NOTIFICATION(message)
END FUNCTION

// Function to Calculate Effort (Placeholder)
FUNCTION CALCULATE_EFFORT(taskID: STRING) -> INTEGER:
    // Implement effort tracking logic
    RETURN 0 // Placeholder
END FUNCTION

// Function to Send Notification (Placeholder)
FUNCTION SEND_NOTIFICATION(message: STRING):
    // Implement actual notification sending logic
    // Example: Send email or Slack message
END FUNCTION

// Function to Read Lines from a File
FUNCTION READ_LINES(filePath: STRING) -> LIST<STRING>:
    // Implement file reading logic
    // Example: Open the file and read all lines into a list
    lines = FILE_READ_ALL_LINES(filePath)
    RETURN lines
END FUNCTION

// Function to Write or Append to a File
FUNCTION APPEND(content: STRING, filePath: STRING):
    // Implement file append logic
    OPEN filePath IN APPEND_MODE
    WRITE content TO filePath
    CLOSE filePath
END FUNCTION

// Function to Insert Content into a File at a Specific Position
FUNCTION INSERT(content: STRING, position: INTEGER, filePath: STRING):
    // Implement file insert logic at specified position
    lines = READ_LINES(filePath)
    INSERT content AT position IN lines
    WRITE_ALL_LINES(lines, filePath)
END FUNCTION

// Function to Replace Content in a File
FUNCTION REPLACE(original: STRING, replacement: STRING, filePath: STRING):
    // Implement file replace logic
    lines = READ_LINES(filePath)
    FOR i FROM 0 TO LENGTH(lines) - 1:
        IF lines[i] CONTAINS original:
            lines[i] = REPLACE_SUBSTRING(lines[i], original, replacement)
        END IF
    END FOR
    WRITE_ALL_LINES(lines, filePath)
END FUNCTION

// Function to Execute a Task with Error Handling and Logging
FUNCTION executeTaskWithRobustness(task: Task, notepad: Notepad):
    TRY:
        executeAndUpdate(task, notepad)
    CATCH Exception e:
        task.status = TaskStatus.FAILED
        task.failureCases = e.message
        logError(e)
        escalateTask(task, notepad)
    END TRY
END FUNCTION

// Function to Implement Concurrency (Placeholder)
FUNCTION executeTasksConcurrently(tasks: LIST<Task>, notepad: Notepad):
    // Implement parallel execution of independent tasks
    FOR EACH task IN tasks PARALLEL:
        executeTaskWithRobustness(task, notepad)
    END FOR
END FUNCTION

// Function to Integrate with Version Control Systems (Placeholder)
FUNCTION integrateWithVersionControl(task: Task):
    // Implement integration with Git or other VCS
    // Example: Commit changes, push to repository
    gitCommit(task)
    gitPush(task)
END FUNCTION

// Function to Integrate with Project Management Tools (Placeholder)
FUNCTION integrateWithProjectManagement(task: Task):
    // Implement integration with Jira, Trello, Asana, etc.
    // Example: Update task status in the project management tool
    updatePMTool(task)
END FUNCTION

// Function to Integrate with CI/CD Pipelines (Placeholder)
FUNCTION integrateWithCICD(task: Task):
    // Implement integration with CI/CD pipelines
    // Example: Trigger automated tests and deployments
    triggerCICD(task)
END FUNCTION

// Function to Collect User Feedback (Placeholder)
FUNCTION collectUserFeedback() -> STRING:
    // Implement feedback collection mechanism
    // Example: Prompt user for feedback or collect from a survey
    feedback = GET_USER_FEEDBACK()
    RETURN feedback
END FUNCTION

// Function to Analyze User Feedback using NLP (Placeholder)
FUNCTION analyzeUserFeedback(feedback: STRING) -> DICTIONARY<STRING, STRING>:
    // Implement NLP to analyze feedback and extract insights
    analysis = NLP_AnalyzeFeedback(feedback)
    RETURN analysis
END FUNCTION

// Function to Incorporate User Feedback into Agent Operations
FUNCTION incorporateUserFeedback(agent: Agent, feedbackAnalysis: DICTIONARY<STRING, STRING>):
    // Implement logic to adjust agent behavior based on feedback
    agent.adjustBehavior(feedbackAnalysis)
END FUNCTION

// Function to Implement Authentication and Authorization (Placeholder)
FUNCTION authenticateUser(credentials: STRING) -> BOOLEAN:
    // Implement authentication logic
    RETURN TRUE // Placeholder
END FUNCTION

// Function to Encrypt Data (Placeholder)
FUNCTION encryptData(data: STRING) -> STRING:
    // Implement data encryption logic
    RETURN ENCRYPTED_DATA // Placeholder
END FUNCTION

// Function to Decrypt Data (Placeholder)
FUNCTION decryptData(encryptedData: STRING) -> STRING:
    // Implement data decryption logic
    RETURN DECRYPTED_DATA // Placeholder
END FUNCTION

// Function to Maintain Audit Trails (Placeholder)
FUNCTION maintainAuditTrail(action: STRING, user: STRING):
    // Implement audit trail logging
    logAudit(action, user)
END FUNCTION

// Function to Provide Detailed Inline Comments (Documentation)
FUNCTION provideDetailedComments():
    // Ensure that all complex logic within functions is well-commented
    // Example: Explain the purpose of each major step within a function
    // This is a non-functional placeholder to indicate the need for documentation
END FUNCTION

// Function to Create External Documentation (Placeholder)
FUNCTION createExternalDocumentation():
    // Implement the creation of comprehensive external documentation
    // Example: Generate Markdown or HTML documentation outlining architecture, functionalities, and usage
    GENERATE_DOCUMENTATION()
END FUNCTION

// Function to Ensure Code Modularity (Placeholder)
FUNCTION ensureCodeModularity():
    // Implement code organization strategies to maintain modularity
    // Example: Separate code into different modules or classes based on functionality
    ORGANIZE_CODE_MODULES()
END FUNCTION

// Function to Initialize MCTS Search Tree
FUNCTION initializeSearchTree(task: Task) -> SearchTree:
    // Initialize the search tree with the current task as the root node
    tree = new SearchTree()
    rootNode = new TreeNode(task)
    tree.root = rootNode
    RETURN tree
END FUNCTION

// Function to Selection Phase of MCTS
FUNCTION selection(tree: SearchTree) -> TreeNode:
    // Select a node to expand using a selection policy (e.g., UCB1)
    node = tree.root
    WHILE node.isFullyExpanded AND node.hasChildren():
        node = node.selectChild() // Implement selection policy
    END WHILE
    RETURN node
END FUNCTION

// Function to Expansion Phase of MCTS
FUNCTION expansion(node: TreeNode):
    // Expand the node by adding a new child node
    newTask = generatePossibleSubTask(node.task)
    newNode = new TreeNode(newTask)
    node.addChild(newNode)
    RETURN newNode
END FUNCTION

// Function to Simulation Phase of MCTS
FUNCTION simulation(node: TreeNode) -> SimulationResult:
    // Simulate the outcome of the task
    result = simulateTask(node.task)
    RETURN result
END FUNCTION

// Function to Backpropagation Phase of MCTS
FUNCTION backpropagation(node: TreeNode, result: SimulationResult):
    // Update the nodes with the simulation result
    WHILE node != NULL:
        node.update(result)
        node = node.parent
    END WHILE
END FUNCTION

// Function to Generate Possible SubTask for Expansion
FUNCTION generatePossibleSubTask(task: Task) -> Task:
    // Use Chain of Thought (CoT) and NLP techniques to generate a possible subtask
    subTaskDescription = CoT_Reasoning(task)
    subTask = new Task()
    subTask.id = generateUniqueTaskID()
    subTask.name = subTaskDescription
    subTask.status = TaskStatus.NOT_PLANNED
    subTask.priority = task.priority
    subTask.estimatedEffort = ESTIMATE_EFFORT(subTaskDescription)
    subTask.assignedPersonnel = ASSIGN_PERSONNEL(subTaskDescription)
    subTask.deadline = CALCULATE_DEADLINE(subTaskDescription)
    subTask.retries = 0
    RETURN subTask
END FUNCTION

// Function to Simulate Task Outcome
FUNCTION simulateTask(task: Task) -> SimulationResult:
    // Simulate the task execution and return the result
    TRY:
        executeSubTask(task)
        IF task.status == TaskStatus.COMPLETED:
            RETURN SUCCESS
        ELSE:
            RETURN FAILURE
    CATCH:
        RETURN FAILURE
    END TRY
END FUNCTION

// Function to Perform MCTS Decision-Making
FUNCTION performMCTS(tree: SearchTree, iterations: INTEGER):
    FOR i FROM 1 TO iterations:
        node = selection(tree)
        IF node.canExpand():
            child = expansion(node)
            result = simulation(child)
            backpropagation(child, result)
        ELSE:
            result = simulation(node)
            backpropagation(node, result)
        END IF
    END FOR
END FUNCTION

// Function to Choose Best Action from MCTS
FUNCTION chooseBestAction(tree: SearchTree) -> TreeNode:
    // Choose the child with the highest visit count or value
    bestChild = tree.root.getBestChild()
    RETURN bestChild
END FUNCTION

// Function to Implement CoT and NLP Self-Regression for Deep Reasoning
FUNCTION CoT_Reasoning(task: Task) -> STRING:
    // Implement Chain of Thought reasoning to generate a detailed subtask description
    reasoningSteps = [
        "Analyze the main objectives of the task.",
        "Identify the key components required to achieve these objectives.",
        "Break down each component into actionable sub-tasks.",
        "Ensure that each sub-task is clear, concise, and achievable."
    ]
    subTaskDescription = ""
    FOR EACH step IN reasoningSteps:
        subTaskDescription += step + " "
    END FOR
    RETURN subTaskDescription.trim()
END FUNCTION

// Function to Estimate Effort based on SubTask Description
FUNCTION ESTIMATE_EFFORT(description: STRING) -> INTEGER:
    // Implement effort estimation logic using NLP
    estimated = NLP_EstimateEffort(description)
    RETURN estimated
END FUNCTION

// Function to Assign Personnel based on SubTask Description
FUNCTION ASSIGN_PERSONNEL(description: STRING) -> STRING:
    // Implement personnel assignment logic using NLP
    personnel = NLP_AssignPersonnel(description)
    RETURN personnel
END FUNCTION

// Function to Calculate Deadline based on SubTask Description
FUNCTION CALCULATE_DEADLINE(description: STRING) -> DATE:
    // Implement deadline calculation logic using NLP
    deadline = NLP_CalculateDeadline(description)
    RETURN deadline
END FUNCTION

// Function to Log Audit Trails
FUNCTION logAudit(action: STRING, user: STRING):
    // Implement audit trail logging
    LOG("Audit: " + action + " by " + user)
END FUNCTION

// Function to Terminate Operation
FUNCTION TERMINATE_OPERATION(reason: STRING):
    // Implement operation termination logic
    LOG("Operation Terminated: " + reason)
    EXIT
END FUNCTION

// Function to Initialize MCTS and Execute Decision-Making
FUNCTION mctsDecisionMaking(task: Task, notepad: Notepad) -> Task:
    // Initialize the search tree
    tree = initializeSearchTree(task)

    // Perform MCTS iterations
    performMCTS(tree, 1000) // Number of iterations can be adjusted

    // Choose the best action based on MCTS
    bestNode = chooseBestAction(tree)

    // Return the selected subtask
    RETURN bestNode.task
END FUNCTION

// Function to Detect and Handle Hallucinations or Context Forgetting
FUNCTION detectAndHandleHallucination(output: STRING, task: Task, notepad: Notepad):
    // Implement coherence and relevance checking using NLP
    IF NOT isOutputCoherent(output, task):
        // Log the incident
        LOG("Hallucination detected in task: " + task.name)

        // Reject the current output
        TERMINATE_OPERATION("Hallucination detected. Rejecting output to prevent project damage.")

        // Log the incident for review
        maintainAuditTrail("Hallucination detected in task execution.", "Agent")

        // Notify stakeholders
        notifyStakeholders("Hallucination detected during task execution. Initiating fail-safe protocols.")

        // Initiate a new conversation environment for task re-analysis
        initiateNewConversationEnvironment()

        // Re-analyze and redefine the task
        newTaskInput = redefineTask(task)
        newMainTask = analyzeUserTask(newTaskInput)
        newNotepad = createNotepad(newMainTask)
        RETURN newMainTask
    END IF
    RETURN task
END FUNCTION

// Function to Check Output Coherence (Placeholder)
FUNCTION isOutputCoherent(output: STRING, task: Task) -> BOOLEAN:
    // Implement coherence and relevance checking using NLP
    coherence = NLP_CheckCoherence(output, task)
    RETURN coherence
END FUNCTION

// Function to Initiate a New Conversation Environment
FUNCTION initiateNewConversationEnvironment():
    // Implement logic to start a new conversation environment
    LOG("Initiating a new conversation environment for task re-analysis.")
    // Placeholder for environment initialization
END FUNCTION

// Function to Redefine Task (Placeholder)
FUNCTION redefineTask(task: Task) -> STRING:
    // Implement logic to redefine the task based on previous failures
    newTaskInput = "Redefine task: " + task.name
    RETURN newTaskInput
END FUNCTION

// Main Workflow

FUNCTION main(taskInput: STRING, userCredentials: STRING, currentUser: STRING, sensitiveInformation: STRING):
    // Security and Access Control
    IF NOT authenticateUser(userCredentials):
        TERMINATE_OPERATION("Authentication Failed")
    END IF

    // Step 1: Analyze and Decompose User Task
    mainTask = analyzeUserTask(taskInput)

    // Step 2: Create Structured Notepad
    notepad = createNotepad(mainTask)

    // Step 3: Initialize MCTS and Perform Decision-Making
    selectedSubTask = mctsDecisionMaking(mainTask, notepad)

    // Execute the selected subtask
    executeTaskWithRobustness(selectedSubTask, notepad)

    // Step 4: Check if Main Task is Completed
    IF all subTasks IN notepad.tasks ARE TaskStatus.COMPLETED:
        summarizeMainTask(notepad, mainTask)
    ELSE:
        // Step 5: Handle Incomplete Main Task
        handleIncompleteMainTask(notepad, mainTask)
    END IF

    // Collect and Incorporate User Feedback
    feedback = collectUserFeedback()
    IF feedback IS NOT EMPTY:
        feedbackAnalysis = analyzeUserFeedback(feedback)
        incorporateUserFeedback(agent, feedbackAnalysis)
    END IF

    // Encrypt Sensitive Data
    encryptedData = encryptData(sensitiveInformation)

    // Maintain Audit Trails
    maintainAuditTrail("Executed main workflow", currentUser)

    // Documentation and Maintainability
    provideDetailedComments()
    createExternalDocumentation()
    ensureCodeModularity()
END FUNCTION

// Execution Example
USER_INPUT = "Latest user task description, such as designing user interface, developing backend API, setting up database, etc."
USER_CREDENTIALS = "user_credentials_here"
CURRENT_USER = "current_user_identifier"
SENSITIVE_INFORMATION = "sensitive_data_here"
main(USER_INPUT, USER_CREDENTIALS, CURRENT_USER, SENSITIVE_INFORMATION)
```

This implementation demonstrates the core functionality of CDTMP, including task management, integration capabilities, security features, and documentation requirements.

---

## Usage

1. **Copy Protocol Text to Cursor**

   - Copy the protocol content into Cursor's **Rules for AI** settings
   - Ensure all protocol components are properly configured
2. **Configure AI Rules**

   - Configure the intelligent agents to follow the CDTMP's processes and methods
   - Set up task analysis parameters
   - Configure performance metrics
   - Set security and compliance rules
3. **Select Model**

   - In Cursor, select the **Claude 3.5 Sonnet** model for conversations
   - Ensure model compatibility with your specific use case
4. **Task Management**

   - Input detailed task descriptions
   - Monitor task decomposition and analysis
   - Track progress through the structured notepad system
   - Review performance metrics and optimization suggestions
5. **Integration & Monitoring**

   - Set up necessary integrations with development tools
   - Monitor task execution and progress
   - Review and act on system feedback
   - Maintain audit trails and documentation

## Contribution Guide

Contributions to the **Cognitive Decision and Task Management Protocol (CDTMP)** are welcome! Please follow these guidelines:

1. **Fork the Repository**

   - Create a personal fork of the project
   - Keep your fork synchronized with the main repository
2. **Create a Feature Branch**

   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Development Guidelines**

   - Follow the established code structure and naming conventions
   - Maintain comprehensive documentation
   - Include detailed comments for complex logic
   - Ensure proper error handling
   - Add appropriate test cases
4. **Testing Requirements**

   - Write unit tests for new features
   - Ensure all existing tests pass
   - Test integration with existing components
   - Verify performance metrics
5. **Commit Your Changes**

   ```bash
   git commit -m 'Add some AmazingFeature'
   ```
6. **Push to the Branch**

   ```bash
   git push origin feature/AmazingFeature
   ```
7. **Documentation**

   - Update relevant documentation
   - Include usage examples
   - Document any new features or changes
   - Update performance metrics if applicable
8. **Open a Pull Request**

   - Provide a clear description of the changes
   - Reference any related issues
   - Include test results and performance metrics
   - Address review comments promptly

Please ensure your code adheres to:

- Project coding standards
- Documentation requirements
- Test coverage guidelines
- Performance benchmarks
- Security best practices

---

## License

This project is licensed under the [MIT License](LICENSE). See the [LICENSE](LICENSE) file for details.

---

## Contact Information

If you have any questions or suggestions, please contact us via:

- **Email**: zihoi.luk@foxmail.com
- **GitHub Issues**: [https://github.com/yourusername/CDTMP/issues](https://github.com/tsekaluk/CDTMP-Agent-Instructions/issues)

---

## Acknowledgments

Thank you to the [Thinking-Claude](https://github.com/richards199999/Thinking-Claude) project for its contributions, as our engineering mainly references this protocol.

We also acknowledge Anthropic's research paper "Building effective agents" [1] which provided valuable theoretical guidance for our development approach.

## References

[1] Schluntz, E., & Zhang, B. (2024). Building effective agents. Anthropic. https://www.anthropic.com/research/building-effective-agents

[2] He, J., Rungta, M., Koleczek, D., Sekhon, A., Wang, F. X., & Hasan, S. (2024). Does Prompt Formatting Have Any Impact on LLM Performance?. arXiv preprint arXiv:2411.10541. https://doi.org/10.48550/arXiv.2411.10541

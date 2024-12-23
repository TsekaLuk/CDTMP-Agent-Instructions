# 认知决策与任务管理协议 (Cognitive Decision and Task Management Protocol, CDTMP)

[中文](README.md) | English

![License](https://img.shields.io/github/license/tsekaluk/CDTMP-Agent-Instructions)

## 简介

**认知决策与任务管理协议 (CDTMP)** 是一种创新性的方法，旨在解决智能体之间在处理高复杂度任务时面临的上下文连续性挑战。基于 Anthropic 关于通过简单、可组合模式构建高效智能体的研究[1]以及关于提示词格式对大语言模型性能影响的研究发现[2]，该协议提供了一种完备、专业、基于工程且可复用的解决方案。通过先进的提示词工程技术，CDTMP 确保在智能体协作过程中，任务的上下文信息得以持续和准确地传递与维护。

---

## 特性

- **上下文连续性维护**：通过复杂的任务分解和跟踪机制，在复杂任务中保持任务上下文的一致性和连续性。
- **工程化设计**：基于系统工程原理，提供全面的任务分析和管理的结构化、模块化解决方案。
- **可复用性**：通过标准化协议，适用于多种智能体和任务类型，有效降低开发成本。
- **提示词工程**：运用先进的自然语言处理技术，优化智能体之间的信息传递和理解。
- **高适应性**：应对智能体之间的相互不了解和快速遗忘，保持协作效率。
- **任务分析与分解**：实现复杂任务智能分解为可管理子任务的高级算法。
- **进度追踪**：通过表情符号状态指示和全面的元数据维护详细的进度记录。
- **性能优化**：包含内置的性能指标和瓶颈识别机制。

## 系统架构

CDTMP 系统由以下关键组件构成：

### 1. 任务分析引擎

- 唯一任务ID生成
- 任务优先级判定
- 项目架构设计
- 代码逻辑优化
- 算法选择与优化
- 模块划分
- 命名规范管理

### 2. 结构化文档系统

- 动态备忘录创建
- 结构化文件命名
- 任务元数据记录
- 进度跟踪
- 性能指标管理

### 3. 执行框架

- 子任务执行管理
- 错误处理和重试机制
- 并发执行能力
- 开发工具集成
- 实时状态更新

### 4. 反馈与优化

- 用户反馈收集
- 性能分析
- 持续改进机制
- 知识转移系统

---

## 主要现细节

以下伪代码展示了 CDTMP 系统的核心实现：

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
    summary += "- **工具执行方法**: " + task.toolExecutionMethod + "\n"
    summary += "- **操作文件对象的相对路径**: " + task.filePath + "\n"
    summary += "- **涉及的上下文主要思想**: " + task.contextIdea + "\n"
    summary += "- **用户的潜在诉求**: " + task.userIntent + "\n"
    summary += "- **容易忽略或误解的任务约束**: " + task.taskConstraints + "\n"
    summary += "- **用户反复强调的要点**: " + task.userEmphasis + "\n"
    summary += "- **任务中失败的案例总结**: " + task.failureCases + "\n"
    summary += "- **耦合的代码文件与关键函数**: " + task.coupledFiles + "\n"
    summary += "- **未来关注的问题或开发经验**: " + task.futureConcerns + "\n"
    summary += "- **可延伸的创新性思考任务**: " + task.innovativeTasks + "\n"

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
    newTaskInput = "重新定义任务：" + task.name
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
USER_INPUT = "用户最新下达的任务描述，例如设计用户界面、开发后台API、设置数据库等。"
USER_CREDENTIALS = "user_credentials_here"
CURRENT_USER = "current_user_identifier"
SENSITIVE_INFORMATION = "sensitive_data_here"
main(USER_INPUT, USER_CREDENTIALS, CURRENT_USER, SENSITIVE_INFORMATION)
```

此实现展示了 CDTMP 的核心功能，包括任务管理、集成能力、安全特性和文档要求。

---

## 使用方法

1. **复制协议文本到 Cursor**

   - 将协议内容复制并粘贴到 Cursor 中的 **Rules for AI** 设置中
   - 确保所有协议组件配置正确
2. **设置 AI 规则**

   - 配置智能体以遵循 CDTMP 的流程和方法
   - 设置任务分析参数
   - 配置性能指标
   - 设置安全和合规规则
3. **选择模型**

   - 在 Cursor 中选择 **Claude 3.5 Sonnet** 模型进行对话
   - 确保模型与您的具体用例兼容
4. **任务管理**

   - 输入详细的任务描述
   - 监控任务分解和分析过程
   - 通过结构化备忘录系统跟踪进度
   - 审查性能指标和优化建议
5. **集成与监控**

   - 设置必要的开发工具集成
   - 监控任务执行和进度
   - 审查并响应系统反馈
   - 维护审计跟踪和文档

## 贡献指南

欢迎为 **认知决策与任务管理协议 (CDTMP)** 贡献代码和提出建议！请遵循以下指南：

1. **Fork 本仓库**

   - 创建项目的个人分支
   - 保持您的分支与主仓库同步
2. **创建特性分支**

   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **开发指南**

   - 遵循既定的代码结构和命名规范
   - 维护全面的文档
   - 为复杂逻辑添加详细注释
   - 确保适当的错误处理
   - 添加适当的测试用例
4. **测试要求**

   - 为新功能编写单元测试
   - 确保所有现有测试通过
   - 测试与现有组件的集成
   - 验证性能指标
5. **提交更改**

   ```bash
   git commit -m 'Add some AmazingFeature'
   ```
6. **推送到分支**

   ```bash
   git push origin feature/AmazingFeature
   ```
7. **文档要求**

   - 更新相关文档
   - 包含使用示例
   - 记录任何新功能或更改
   - 必要时更新性能指标
8. **打开 Pull Request**

   - 提供清晰的更改描述
   - 引用相关问题
   - 包含测试结果和性能指标
   - 及时处理审查意见

请确保您的代码符合：

- 项目编码标准
- 文档要求
- 测试覆盖率指南
- 性能基准
- 安全最佳实践

---

## 许可证

本项目采用 [MIT 许可证](LICENSE) 许可。详情请参阅 [LICENSE](LICENSE) 文件。

---

## 联系信息

如果您有任何问题或建议，请通过以下方式联系：

- **邮箱**: zihoi.luk@foxmail.com
- **GitHub Issues**: [https://github.com/yourusername/CDTMP/issues](https://github.com/tsekaluk/CDTMP-Agent-Instructions/issues)

---

## 致谢

感谢 [Thinking-Claude](https://github.com/richards199999/Thinking-Claude) 项目，因为在我们的工程中主要引用了这个协议。

我们同时感谢 Anthropic 的研究论文 "Building effective agents" [1]，该论文为我们的开发方法提供了宝贵的理论指导。

## 参考文献

[1] Schluntz, E., & Zhang, B. (2024). Building effective agents. Anthropic. https://www.anthropic.com/research/building-effective-agents

[2] He, J., Rungta, M., Koleczek, D., Sekhon, A., Wang, F. X., & Hasan, S. (2024). Does Prompt Formatting Have Any Impact on LLM Performance?. arXiv preprint arXiv:2411.10541. https://doi.org/10.48550/arXiv.2411.10541

# Hands-On: Microsoft Fabric Data Agents for Executives

## 🎯 Hands-On Objectives

This hands-on session is designed to demonstrate to executives the power of **Microsoft Fabric Data Agents**. You will discover how AI can transform complex data analysis into natural conversations, enabling decision-makers to quickly gain insights without technical skills.

### Estimated Duration: 45 minutes
- Scenario 1: 20 minutes
- Scenario 2: 25 minutes

---

## 📋 Prerequisites

- Access to Microsoft Fabric with enabled capacity
- OneLake Explorer installed on Windows Desktop. Download Onelake Explorer ([here](https://www.microsoft.com/en-us/download/details.aspx?id=105222)).
- Admin rights on Fabric workspace
- Provided `budget_analysis.csv` file (see Datasets section)

---

## 🎭 Scenario 1: From Windows Desktop to Data Agents via OneLake Explorer

### Business Context
*You are a financial director who wants to quickly analyze budget data stored locally. Instead of waiting for the IT team or an analyst, you want to access insights directly through AI.*

### Detailed Steps

#### 1. Starting from Windows Desktop
1. **Open Windows Explorer**
   - Navigate to the folder containing your data files
   - Locate the `budget_analysis.csv` file
     
   ![Onelake Explorer](https://github.com/EtienneSIG/-HO-Microsoft-Fabric-DataAgent/blob/main/img/Onelake%20Explorer.png)


#### 2. Connection via OneLake Explorer
1. **Launch OneLake Explorer**
   - Right-click on the OneLake icon in the taskbar
   - Select "Open OneLake Explorer"
   
2. **Authentication**
   - Sign in with your Microsoft 365 credentials
   - Select the appropriate Fabric workspace

#### 3. Data Loading
1. **Drag and Drop the File**
   - Drag `budget_analysis.csv` from Windows Explorer
   - Drop into your OneLake workspace
   
2. **Loading Validation**
   - Verify that the file appears in OneLake
   - Note the automatic data preview

#### 4. Data Agent Activation
1. **Access Fabric Online**
   - Click right on the file "View item online" from OneLake Explorer
   - Navigate to the "Files" section to see your csv file
   - Click right on csv file, then ![Load to tables](https://github.com/EtienneSIG/-HO-Microsoft-Fabric-DataAgent/blob/main/img/load%20to%20table.png) and !["New table"](https://github.com/EtienneSIG/-HO-Microsoft-Fabric-DataAgent/blob/main/img/New%20table.png)
   
   ![Load to tables](https://github.com/EtienneSIG/-HO-Microsoft-Fabric-DataAgent/blob/main/img/Load%20csv%20into%20table.png)
   
2. **Create the Data Agent**
   - Locate the newly created `budget_analysis` table
   - Click the **"Add Data Agent"** button
   - Configure the Data Agent name: "Budget Assistant"

#### 5. First Conversational Test
**Questions to ask the Data Agent:**
- "What is our biggest expense category?"
- "Show me budget evolution by quarter"
- "Which departments exceeded their budget?"

### 💡 Key Points for Executives
- **Simplicity**: From your desktop to AI in 5 clicks
- **Autonomy**: No need to wait for technical teams
- **Immediacy**: Instant insights in natural language

---

## 🏗️ Scenario 2: Building a Data Agent Based on a Semantic Model

### Business Context
*As a CFO, you want to create a permanent AI assistant that understands your company's financial structure and can answer complex questions across multiple data sources.*

### Solution Architecture
```
📊 Data Sources
    ↓
🔄 Fabric Semantic Model
    ↓
🤖 Intelligent Data Agent
    ↓
💬 Conversational Interface
```

### Construction Steps

#### 1. Fabric Workspace Preparation
1. **Access Fabric Portal**
   - Sign in to `app.fabric.microsoft.com`
   - Create a new workspace: "Executive Analytics"

2. **Capacity Configuration**
   - Verify Premium capacity allocation
   - Enable Data Agent features

#### 2. Data Import and Preparation
1. **Load Main Dataset**
   - Go to "Get Data" > "Upload files"
   - Select `budget_analysis.csv`
   - Preview and validate data types

2. **Data Transformation (if needed)**
   - Use Power Query to clean data
   - Create calculated columns (e.g., budget vs actual variance)
   - Define relationships between tables (if multiple sources)

#### 3. Semantic Model Construction
1. **Create New Semantic Model**
   - In Fabric, select "New" > "Semantic Model"
   - Name: "Corporate Budget Model"

2. **Define DAX Measures**
   ```dax
   Total Budget = SUM('Budget'[Budget_Amount])
   Total Actual = SUM('Budget'[Actual_Amount])
   Budget Variance = [Total Actual] - [Total Budget]
   Budget Variance % = DIVIDE([Budget Variance], [Total Budget], 0)
   ```

3. **Configure Hierarchies**
   - Create temporal hierarchy: Year > Quarter > Month
   - Create organizational hierarchy: Division > Department > Team

#### 4. Advanced Data Agent Creation
1. **Access Data Agents**
   - In the Fabric ribbon, click "Data Agents"
   - Select "Create Data Agent"

2. **Data Agent Configuration**
   - **Name**: "Executive Budget Assistant"
   - **Description**: "AI assistant for executive budget analysis"
   - **Data Source**: Select "Corporate Budget Model"

3. **Agent Customization**
   - Define business context in instructions
   - Configure standard responses for frequent questions
   - Enable automatic visualizations

#### 5. Testing and Optimization
**Sophisticated test scenarios:**

1. **Performance Analysis**
   - "How are our different divisions performing against budget?"
   - "Identify concerning trends in our spending"

2. **Predictions and Recommendations**
   - "At this rate, what will be our budget overrun by year-end?"
   - "Which departments should reduce their spending?"

3. **Comparative Analysis**
   - "Compare Q3 vs Q2 performance by division"
   - "Show me the most significant variances"

### 🚀 Advanced Features to Demonstrate

#### Contextual Intelligence
- Understanding company-specific financial jargon
- Recognition of critical KPIs
- Proactive analysis suggestions

#### Dynamic Visualizations
- Automatic generation of relevant charts
- Adaptive dashboards based on questions
- Direct export to PowerPoint/Excel

#### Executive Collaboration
- Insight sharing with leadership team
- Question and answer history
- Critical metrics alerts

---

## 📊 Dataset : Budget Analysis

### Structure du fichier `budget_analysis.csv`

| Column | Type | Description | Example |
|---------|------|-------------|---------|
| Date | Date | Transaction date | 2024-01-15 |
| Division | Text | Company division | Sales, Marketing, IT, HR |
| Department | Text | Specific department | Digital Marketing, Cybersecurity |
| Category | Text | Expense category | Personnel, Software, Travel |
| Budget_Amount | Numeric | Budgeted amount | 50000 |
| Actual_Amount | Numeric | Actual amount spent | 52500 |
| Currency | Text | Currency | EUR |
| Project_Code | Text | Project code (optional) | PROJ001 |
| Responsible_Manager | Text | Responsible manager | John Smith |
| Quarter | Text | Quarter | Q1 2024 |

### Dataset Generation
*The CSV file will be created with 500 lines of realistic data covering a complete fiscal year, including different scenarios: budget overruns, savings, exceptional projects, etc.*

---

## ✅ Success Criteria

### For Scenario 1
- [ ] Successful data loading via OneLake Explorer
- [ ] Data Agent creation in less than 5 minutes
- [ ] Obtaining 3 relevant insights through conversation

### For Scenario 2
- [ ] Functional semantic model with DAX measures
- [ ] Data Agent responding to complex questions
- [ ] Automatic generation of adapted visualizations

---

## 🎓 Key Messages for Executives

### Immediate ROI
- **Time-to-Insight Reduction**: From days to minutes
- **Decision Autonomy**: No more technical dependencies
- **Data Democratization**: Accessible at all levels

### Digital Transformation
- **Conversational AI**: Natural interface with data
- **Self-Service Analytics**: Team empowerment
- **Intelligent Governance**: Security and control maintained

### Competitive Advantage
- **Faster Decisions**: Increased responsiveness
- **Deeper Insights**: AI detects hidden patterns
- **Continuous Innovation**: Evolving Microsoft platform

---

## 📞 Support and Resources

- **Official Documentation**: [Microsoft Fabric Data Agents](https://learn.microsoft.com)
- **Additional Training**: Microsoft Learn paths
- **Technical Support**: Your IT team or Microsoft partner

---


*This hands-on was designed to demonstrate the transformative power of Microsoft Fabric Data Agents in an executive context. The goal is to show how AI can become a true decision-making assistant for leaders.*












# N8N Test Case Generation Projects

This repository contains two AI-powered N8N workflow solutions for automating test case generation based on JIRA tickets and Product Requirement Documents (PRDs).

## 📋 Project Overview

These workflows leverage AI agents powered by Groq LLM to intelligently generate structured test cases by analyzing:
- **JIRA Tickets** - Feature descriptions, acceptance criteria, and requirements
- **Product Requirement Documents (PRDs)** - Detailed specifications from Google Docs
- **Business Rules & Constraints** - Technical and functional requirements

## 🚀 Projects

### Project 1: Test Case Generation from JIRA & PRD
**Directory:** `n8n-P1-TestCaseGenUsingJIRA_PRD/`

This workflow reads a JIRA ticket and its associated PRD, then generates structured test cases based strictly on documented requirements.

**Key Features:**
- 🤖 AI Agent with 15+ years of Senior QA Engineer expertise
- 📖 Reads JIRA issues directly
- 📄 Extracts and analyzes PRDs from Google Docs
- ✅ Generates test cases in JIRA-compatible tabular format
- ⚠️ Strict adherence to documented requirements (no assumptions or hallucinations)
- 💬 Chat-triggered workflow

**Workflow Components:**
- Chat Trigger Node
- AI Agent Node (with strict system instructions)
- Groq LLM Node (openai/gpt-oss-120b model)
- JIRA Tool Node (retrieves issue details)
- Google Docs Tool Node (retrieves PRD content)

**Usage Example:**
```
"Create test cases for app.bw.com for Jira ID BW-123"
```

---

### Project 2: Test Case Generation with Excel/Sheet Export
**Directory:** `n8n-P2-TestGenPushToExcel/`

Enhanced version of Project 1 that not only generates test cases but also automatically pushes them to a Google Sheet or Excel file.

**Key Features:**
- 🤖 AI-powered test case generation
- 📊 Automatic export to Google Sheets
- 📈 Real-time updates in specified worksheets
- 🔄 Seamless integration with spreadsheet tools
- 📋 Structured data for easy tracking and management

**Usage Example:**
```
"Read the PRD and JIRA ticket SCRUM-8 and provide 10 positive test cases. 
Push the test cases to the specified Google Sheet."
```

---

## 🔑 Key Features (Both Projects)

### Intelligent Test Case Generation
- ✅ Creates test cases strictly from documented requirements
- ✅ Includes feature descriptions, acceptance criteria, and business rules
- ✅ Identifies technical constraints and dependencies
- ✅ No assumptions or hypothetical scenarios

### Core Instructions
The AI Agent follows strict guidelines:
- 🚫 **No Assumptions** - Only uses explicitly documented information
- 🚫 **No Hallucinations** - Avoids inferring requirements
- 🚫 **No Hypothetical Flows** - Sticks to defined acceptance criteria
- ✅ **Explicit Edge Cases Only** - Documents what's specifically mentioned

### Integration Points
- **JIRA** - Direct integration for ticket retrieval
- **Google Docs** - PRD document access and analysis
- **Google Sheets** (P2 only) - Automatic test case export
- **Groq LLM** - Advanced AI model for intelligent analysis

---

## 📁 File Structure

```
N8N-Projects/
├── README.md (this file)
├── n8n-P1-TestCaseGenUsingJIRA_PRD/
│   ├── P1.md                    (Core instructions and workflow details)
│   ├── prompt.md                (System prompts for AI Agent)
│   └── test.md                  (Test documentation)
└── n8n-P2-TestGenPushToExcel/
    ├── p1                       (Project configuration)
    ├── prompt.md                (Generation prompts)
    ├── prompt-new               (Updated prompts)
    └── promptUser.md            (User-facing instructions)
```

---

## 🛠️ Setup Requirements

### Prerequisites
- **N8N Workflow Tool** - Installed and configured
- **Groq API Key** - For LLM access (openai/gpt-oss-120b model)
- **JIRA Integration** - API credentials for your JIRA instance
- **Google API Credentials** - For accessing Docs and Sheets
- **Google Docs Link** - Containing your PRD
- **Google Sheet** (P2 only) - For test case export

### Environment Variables
Configure the following in your N8N instance:
```
GROQ_API_KEY=your_groq_api_key
JIRA_API_KEY=your_jira_api_key
JIRA_DOMAIN=your_jira_domain
GOOGLE_CREDENTIALS=your_google_credentials
```

---

## 📖 How It Works

### Workflow Steps

1. **Trigger** - User sends a chat message with a JIRA ID
2. **Read Sources** - AI Agent retrieves JIRA ticket and PRD
3. **Analyze** - Extracts requirements, acceptance criteria, and business rules
4. **Generate** - Creates structured test cases
5. **Format** - Outputs in JIRA-compatible tabular format
6. **Export** (P2 only) - Pushes test cases to Google Sheet

---

## 🎯 Use Cases

- **Automated Test Case Generation** - Reduce manual effort in test planning
- **Requirement Verification** - Ensure test cases match documented specs
- **Compliance & Audit Trail** - Maintain records of test case origins
- **Agile Development** - Quick test case generation for sprint planning
- **Cross-Team Collaboration** - Share test cases directly in spreadsheets

---

## 📝 Example Output

Test cases are generated in a structured tabular format:

| Test Case ID | Title | Steps | Expected Result | Status |
|---|---|---|---|---|
| TC-001 | Feature validation | 1. Open app<br>2. Navigate to feature | Feature loads successfully | ✅ |
| TC-002 | Error handling | 1. Enter invalid data<br>2. Submit form | Error message displayed | ✅ |

---

## 🤝 Contributing

To extend or modify these workflows:
1. Clone the repository
2. Update the prompt files with new AI instructions
3. Test the workflows in your N8N instance
4. Commit and push changes

---

## 📞 Support

For issues or questions:
- Check the individual project documentation in respective folders
- Review the prompt files for system instructions
- Verify JIRA and Google API integrations

---

## 📄 License

This project is part of the AI Tester Blueprint series.

---

**Last Updated:** February 20, 2026

# manual-testing-saucedemo
 SauceDemo Manual Testing Portfolio

 Project Overview
A comprehensive manual testing portfolio demonstrating professional QA methodologies by testing the SauceDemo e-commerce demo application. This project showcases end-to-end testing capabilities including test planning, execution, defect reporting, and summary analysis.

Application: [SauceDemo.com](https://www.saucedemo.com/)  
Module Tested: User Authentication (Login Functionality)  
Testing Types: Functional, Security, Performance, Accessibility, Usatility

 Why This Portfolio?
This repository demonstrates real-world QA skills:
Strategic Test Planning - Risk-based approach
Comprehensive Test Execution - 12 detailed test cases
Professional Bug Reporting - 5 documented defects  
Security Testing - CSRF, session management vulnerabilities
Accessibility Compliance - WCAG 2.1 AA testing
Performance Validation - Network and load testing
Professional Documentation - Industry-standard formats

Key Metrics
| Metric | Result |
|--------|--------|
| **Test Cases Executed** | 12 |
| **Test Pass Rate** | 83% (10/12 passed) |
| **Defects Found** | 5 |
| **Critical Issues** | 1 (Security) |
| **Medium Issues** | 3 (UX, Security, Accessibility) |
| **Low Issues** | 1 (Performance) |

 Repository Structure
 manual-testing-saucedemo
├──  README.md # Project overview (this file)
├──  Test_Plan.md # Comprehensive testing strategy
├──  Test_Scenarios.md # High-level test scenarios
├──  Test_Summary_Report.md # Final testing results & analysis
├── 📂 Test_Cases/ # 12 detailed test cases
│ ├──  TC001_Login_Valid_Credentials.md
│ ├──  TC002_Login_Problem_User.md
│ ├──  TC003_Performance_Glitch_User.md
│ ├──  TC004_Session_Persistence.md
│ ├──  TC005_Invalid_Password_Handling.md
│ ├──  TC006_Post_Logout_Security.md
│ ├──  TC007_Page_Load_Performance.md
│ ├──  TC008_Network_Issue_Handling.md
│ ├──  TC009_Screen_Reader_Accessibility.md
│ ├──  TC010_Responsive_Design.md
│ ├──  TC011_HTTP_Method_Validation.md
│ └──  TC012_Error_Code_Validation.md
├── 📂 Bug_Reports/ # 5 professional bug reports
│ ├──  1_SECURITY_CSRF_Protection_Missing.md
│ ├──  2_UX_No_Loading_Indicators.md
│ ├──  3_SECURITY_Back_Button_Cache_Issue.md
│ ├──  4_ACCESSIBILITY_WCAG_Violations.md
│ └──  5_PERFORMANCE_Slow_Network_Handling.md



 Critical Findings

High Severity (1)
CSRF Protection Missing- Login form vulnerable to Cross-Site Request Forgery attacks

Medium Severity (3)
No Loading Indicators - Poor UX during authentication delays (3-7 seconds)
Cached Pages After Logout - Sensitive data briefly exposed via back button
Accessibility Violations - WCAG 2.1 AA compliance gaps identified

Low Severity 
Poor Slow Network Handling - No timeout or feedback on Slow 3G connections

Testing Methodology

 1. Test Planning
 Risk-based testing approach
 Clear entry/exit criteria defined
 12 test cases across 4 categories

 2. Test Execution
 Functional Testing: Positive/Negative scenarios
 Security Testing: CSRF, session management, input validation
 Performance Testing: Load times, network conditions
 Accessibility Testing: Screen reader compatibility, WCAG compliance
 UI/UX Testing: Responsive design, usability

 3. Defect Reporting
 Professional bug report templates
 Clear reproduction steps
 Impact analysis with severity/priority
 Technical recommendations for fixes

 4. Results Analysis
 Comprehensive test summary
 Metrics and KPIs
 Recommendations for improvements
 Evidence-based conclusions
 How to Navigate This Portfolio

For Recruiters & Hiring Managers:
1. Start with `Test_Summary_Report.md` for overall results
2. Review*2-3 test cases in `Test_Cases/` folder
3. Examine bug reports in `Bug_Reports/` folder
4. Check test strategy in `Test_Plan.md`

 For QA Professionals & Learners:
1. Clone the repository: `git clone [your-repo-url]`
2. Execute tests on [SauceDemo.com](https://www.saucedemo.com/)
3. Compare findings with documented results
4. Use as a reference for professional test documentation

 Tools & Technologies Used
 Browser: Chrome DevTools (Network, Performance, Console, Lighthouse)
 Screen Reader: NVDA 2023.3 for accessibility testing
 Network Simulation: Chrome DevTools throttling (Slow 3G, Offline)
 Documentation: Markdown, GitHub for version control
 Methodology: Risk-based testing, exploratory testing

 Skills Demonstrated
| Skill Category | Specific Skills |
|---------------|-----------------|
| Test Planning | Risk analysis, scope definition, strategy development |
| Test Design | Equivalence partitioning, boundary value analysis, error guessing |
| Test Execution | Manual testing, exploratory testing, regression testing |
| Defect Management | Bug reporting, severity/priority assignment, tracking |
| Security Testing | CSRF, session management, input validation |
| Accessibility Testing | WCAG compliance, screen reader testing, keyboard navigation |
| Performance Testing | Load time measurement, network condition testing |
| Documentation | Test cases, bug reports, summary reports, README files |

 License & Attribution
This portfolio is created for educational and demonstration purposes only.

SauceDemo Application: Demo e-commerce site for testing practice
Content: Original test cases, bug reports, and documentation created by (Shristi Acharya)





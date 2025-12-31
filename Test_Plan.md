 SauceDemo Login Module - Test Plan

 Document Information
| Field | Details |
|-------|---------|
| Project | SauceDemo E-commerce Demo |
| Module | User Authentication (Login) |
| Test Lead | Shristi Acharya |
| Version | 1.0 |
| Date | December 2025 |
| Status | Approved |

 1. Introduction
This document outlines the testing strategy for the SauceDemo login functionality. The login module is critical as it's the entry point to the application and handles sensitive user credentials.

2. Test Objectives
 Validate authentication works correctly for all user types
 Identify security vulnerabilities and ensure data protection
 Verify accessibility compliance (WCAG 2.1 AA)
 Ensure performance under various conditions
 Confirm cross-browser and responsive compatibility
 Test error handling and edge cases

 3. Scope

 In-Scope
  Login page UI/UX
  Authentication functionality
  Error handling and validation
  Security aspects (CSRF, password protection)
  Accessibility features
  Performance metrics
  Cross-browser compatibility
  Mobile responsiveness

 Out-of-Scope
  Registration functionality
  Password reset flow
  Other application modules (cart, checkout, inventory)
  Database testing
  Load/stress testing
  API testing (beyond authentication endpoint)

   4. Testing Approach

4.1 Test Types Coverage
| Test Type | Percentage | Focus Areas |
|-----------|------------|-------------|
| Functional Testing | 40% | Positive/Negative scenarios, validation |
| Security Testing | 25% | CSRF, XSS, SQL injection, session management |
| UI/UX Testing | 15% | Responsive design, usability, accessibility |
| Performance Testing | 15% | Load times, network conditions |
| Compatibility Testing | 5% | Cross-browser, mobile devices |

4.2 Risk-Based Testing Strategy
High Risk → Test First & Thoroughly:
- Security vulnerabilities (CSRF, session hijacking)
- Core login functionality
- Data protection (password handling)

Medium Risk → Test Completely:
- Error handling
- Accessibility compliance
- Performance under stress

Low Risk → Test Basic Scenarios:
- UI responsiveness
- Minor edge cases
- Cosmetic issues

5. Test Environment

 5. Test Environment

 5.1 Primary Test Environment
| Component | Specification | Purpose |
|-----------|--------------|---------|
| Application URL | https://'www.saucedemo.com/' | Production-like demo environment |
| Browser | Chrome 120.0.6099.110 | Primary testing browser |
| OS | Windows 11 Pro (Build 22631) | Desktop testing platform |
| Network | Broadband (100 Mbps) + DevTools throttling | Performance simulation |
| Screen Reader | NVDA 2023.3 | Accessibility testing |
| Testing Tools | Chrome DevTools, Postman, GitHub | Execution and documentation |

5.2 Environment Limitations & Workarounds
| Limitation | Workaround | Impact |
|------------|------------|--------|
| Single environment only | Use browser profiles for different user states | Low |
| No test/QA environment | Test directly on demo site (accepted for portfolio) | Medium |
| Limited mobile devices| Use Chrome DevTools device emulation | Low |
| No backend access | Monitor network requests and responses | Medium |

 5.3 Environment Validation Checklist
 Application accessible via URL
 Chrome DevTools functional
 Network throttling working
 Screen reader software installed
 Screenshot capture enabled
 All test accounts available

 5.2 Test Data
| Data Type | Values | Purpose |
|-----------|---------|---------|
| Valid Users | standard_user, problem_user, performance_glitch_user | Positive testing |
| Invalid Users | wrong_user, locked_out_user | Negative testing |
| Passwords | secret_sauce, wrong_password, SQL injection strings | Security testing |
| Network Profiles | Fast 3G, Slow 3G, Offline | Performance testing |

6. 12 Key Test Cases (Detailed)

Category 1: Functional & Positive Testing (3 Tests)**

TC-001: Valid Credentials Login
Objective: Verify standard user can login successfully
Priority: P0 (Critical)
Steps: Enter standard_user/secret_sauce → Click Login
Expected: Redirect to inventory, products displayed

TC-002: Problem User Login
 Objective: Verify problem_user account works (with known UI issues)
 Priority: P1 (High)
 Steps: Login as problem_user → Observe UI anomalies
 Expected: Login success, note visual defects

TC-003: Performance Glitch User
 Objective: Test handling of delayed authentication
 Priority: P2 (Medium)
 Steps: Login as performance_glitch_user → Time response
 Expected: 2-5 second delay, eventual success

Category 2: Security Testing (3 Tests)
TC-004: Invalid Password Handling
 Objective: Verify error handling for wrong credentials
 Priority: P1 (High)
 Steps: Enter valid user + wrong password
 Expected: Clear error, password field cleared

TC-005: Post-Logout Security
 Objective: Ensure cached pages not accessible after logout
 Priority: P1 (High)
 Steps: Login → Logout → Press back button
 Expected: Redirect to login, no cached access

TC-006: HTTP Method Validation
  Objective: Verify POST method used (not GET)
  Priority: P2 (Medium)
  Steps: Monitor network request method
  Expected: POST method, credentials in body (not URL)

Category 3: Performance Testing (3 Tests)

TC-007: Page Load Performance
  Objective: Measure login page load time
  Priority: P2 (Medium)
  Steps: Clear cache → Load page → Record time
  Expected: 3 seconds on Fast 3G

TC-008: Network Issue Handling
  Objective: Test login on slow/poor network
  Priority: P2 (Medium)
  Steps: Set to Slow 3G → Attempt login
  Expected: Appropriate loading indicators, graceful handling

TC-009: Session Persistence
  Objective Verify session remains active
  Priority: P3 (Low)
  Steps: Login → Wait 15 minutes → Refresh
  Expected: Still logged in, session intact

Category 4: Accessibility & UI Testing (3 Tests)

TC-010: Screen Reader Compatibility
  Objective: Verify WCAG compliance for screen readers
  Priority: P2 (Medium)
  Steps: Test with NVDA/JAWS → Verify announcements
  Expected: Proper labels, error announcements, keyboard nav

TC-011: Responsive Design
  Objective: Test mobile responsiveness
  Priority: P3 (Low)
  Steps: Test on 320px, 768px devices → Verify layout
  Expected: Responsive layout, touch-friendly, no horizontal scroll

TC-012: Error Message Validation
  Objective: Verify API error responses
  Priority: P3 (Low)
  Steps: Submit invalid credentials → Check network response
  Expected: Appropriate HTTP codes, no sensitive info exposed

 7. Entry & Exit Criteria

 7.1 Entry Criteria (When to Start Testing)
 Login page deployed to test environment
   Test cases reviewed and approved
   Test data prepared
   Environment setup complete
  Access credentials available

 7.2 Exit Criteria (When to Stop Testing)
  All 12 test cases executed
  Critical/High severity defects fixed and retested
  95% test case pass rate achieved
  Performance benchmarks met (<3s load time)
  Accessibility issues documented
  Test summary report completed

 8. Defect Management

 8.1 Defect Classification
| Severity | Response Time | Definition |
|----------|---------------|------------|
| Critical | 24 hours | Blocks testing, security vulnerability |
| High | 48 hours | Major functionality broken |
| Medium | 1 week | Minor issue, workaround exists |
| Low | Next release | Cosmetic, enhancement |

8.2 Defect Tracking
 Tool: GitHub Issues
 Template: Bug_Report.md
 Required Fields: Steps, Expected, Actual, Evidence
Review Process: Daily defect triage meetings

 9. Test Deliverables
| Deliverable | Description | Owner |
|-------------|-------------|-------|
| Test Cases | 12 detailed test cases | QA Team |
| Bug Reports | Documented defects | QA Team |
| Test Data | Credentials, test inputs | QA Team |
| Test Summary | Final report with metrics | QA Lead |
| Evidence | Screenshots, logs | QA Team |



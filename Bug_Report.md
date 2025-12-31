Bug_Report
├── 1_SECURITY_CSRF_Protection_Missing.md
├── 2_UX_No_Loading_Indicators.md
├── 3_SECURITY_Back_Button_Cache_Issue.md
├── 4_ACCESSIBILITY_WCAG_Violations.md
└── 5_PERFORMANCE_Slow_Network_Handling.md


Detailed description
i.BUG-001: Missing CSRF Protection in Login Form

Severity: High  
Priority: P1 (Immediate)  
Module: Authentication  
Status: New  
Found: TC-012 (HTTP Method Validation)

 Description
i.Login form is vulnerable to Cross-Site Request Forgery (CSRF) attacks. Attackers can trick users into submitting unauthorized login requests.

 Steps to Reproduce
1. Go to https://www.saucedemo.com/
2. Open Chrome DevTools (F12)
3. Submit login with any credentials
4. Check Network tab → authentication request
5. ISSUE: No CSRF token in request payload

 Expected vs Actual
| Expected | Actual |
|----------|--------|
| CSRF token in form | No token present |
| Server validates token | No validation |
| Protected from CSRF attacks | Vulnerable |

 Impact
High Risk: Unauthorized login possible
  Compliance: Security standard violation
  Fix: Add CSRF token validation

 Recommendation
 <!-- Add to login form -->
<input type="hidden" name="csrf_token" value="{{csrf_token}}">


ii.MEDIUM PRIORITY UX BUG
BUG-002: No Loading Feedback During Authentication

Severity: Medium  
Priority: P2 (High)  
Module: User Experience  
Status: New  
Found: TC-009 (Performance Glitch)

 Description
During slow authentication (3-7 seconds), users get no visual feedback. Button appears frozen, causing confusion and multiple clicks.

 Steps to Reproduce
1. Login as performance_glitch_user
2. Click LOGIN button
3. Wait 3-7 seconds
4. ISSUE: No loading spinner, no feedback

User Experience Impact
- Confusion: "Did it work?"
- Multiple Clicks: Users click repeatedly
- Perception: Feels like broken app
- Abandonment: May leave page

Expected vs  Actual
| Expected | Actual |
|----------|--------|
| Loading spinner within 500ms | No feedback for 3+ seconds |
| Button disabled during process | Button appears frozen |
| "Logging in..." text | No status text |



BUG-003: Cached Pages Visible After Logout

Severity: Medium  
Priority: P2 (High)  
Module: Session Security  
Status: New  
Found: TC-006 (Post-Logout Security)

 Description
After logout, pressing browser back button shows cached sensitive pages (inventory, cart) for 1-2 seconds before redirect.

 Steps to Reproduce
1. Login → Add items to cart → Logout
2. Press browser back button (←)
3. **ISSUE:** Sees cached inventory page briefly
4. Sensitive data exposed before redirect

 Data Exposure
- Product prices visible
- Cart contents shown
- User activity briefly displayed

 Expected vs Actual
| Expected | Actual |
|----------|--------|
| Immediate redirect | 1-2 second delay |
| No cached data shown | Sensitive data visible |
| Proper cache headers | Missing no-store header |

 Recommendation
 Add to protected page headers
 Cache-Control: no-store, no-cache
 Pragma: no-cache
 Expires: 0


iv.BUG-004: Multiple Accessibility Issues

Severity: Medium  
Priority: P2 (Medium)  
Module: Accessibility  
Status: New  
Found: TC-010 (Screen Reader Testing)

 Description
Login page fails multiple WCAG 2.1 AA criteria, affecting screen reader users.

 Issues Found
 Missing form label - No aria-label on form
 Empty alt text- Logo has alt=""
 Placeholder as label - No proper <label> elements
 Unlabeled buttons- Error X buttons lack names

 Screen Reader Experience
Current: "Username, edit, required"
Missing: Context that this is a login form



v.BUG-005: Poor Experience on Slow Networks

Severity: Low  
Priority: P3 (Low)  
Module: Performance  
Status: New  
Found: TC-011 (Network Issues)

Description
On Slow 3G networks, login takes 7+ seconds with no feedback and no timeout handling.

 Steps to Reproduce
1. Chrome DevTools → Network → "Slow 3G"
2. Attempt login
3. ISSUE: 7.1 second delay, no loading indicator
4. ISSUE: No timeout (could hang forever)

Performance Metrics
Slow 3G: 7.1 second delay
No feedback: Entire delay period
No timeout: Infinite hang possible
User confusion: "Is it working?"

Expected vs Actual Outcome
| Expected | Actual |
|----------|--------|
| Loading indicator | No feedback |
| 10-second timeout | No timeout |
| Network error message | Just hangs |
| Retry option | No retry option |



Hence,I documented 5 bugs covering security, UX, accessibility, and performance. Each is concise but complete with reproduction steps and fixes. For eg: I found a CSRF vulnerability that's high severity because it could allow unauthorized access.


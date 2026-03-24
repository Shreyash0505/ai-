# FinTrack - Complete Project Documentation Guide

## Document Structure for Word File

---

## SECTION 1: PROJECT OVERVIEW

### 1.1 Title Page
- Project Name: FinTrack - Personal Finance Management System
- Your Name, Roll Number, Department
- Guide Name
- College Name
- Academic Year
- Date of Submission

### 1.2 Abstract (1 page)
FinTrack is a web-based personal finance management application built using Django 6, SQLite, Bootstrap 5, and Chart.js. The system enables users to track expenses, manage income, set budget limits, monitor subscriptions, and achieve savings goals through an intuitive dashboard with real-time analytics and visualizations.

**Key Features:**
- User authentication and profile management
- Expense tracking with category-based filtering
- Income management with multiple sources
- Monthly budget limits with alerts
- Subscription tracker with auto-billing
- Savings goals with progress tracking
- Data export (CSV) with advanced filters
- Dark mode support
- Mobile-responsive design
- Admin panel for user management

**Technology Stack:**
- Backend: Django 6.0.2 (Python)
- Database: SQLite3
- Frontend: Bootstrap 5.3, Chart.js 4.4
- Icons: Bootstrap Icons 1.11
- Additional: python-dateutil, Pillow

---

## SECTION 2: SYSTEM REQUIREMENTS

### 2.1 Hardware Requirements
- Processor: Intel Core i3 or equivalent
- RAM: 4GB minimum, 8GB recommended
- Storage: 500MB free space
- Display: 1366x768 minimum resolution

### 2.2 Software Requirements
- Operating System: Windows 10/11, macOS, or Linux
- Python: 3.10 or higher
- Web Browser: Chrome, Firefox, Safari, or Edge (latest versions)
- Code Editor: VS Code, PyCharm, or any Python IDE

### 2.3 Dependencies (requirements.txt)
```
Django==6.0.2
Pillow==11.1.0
python-dateutil==2.9.0
```

---

## SECTION 3: SYSTEM ARCHITECTURE

### 3.1 Architecture Diagram
[INSERT: High-level architecture diagram showing]
- Client Layer (Browser)
- Presentation Layer (Django Templates + Bootstrap)
- Business Logic Layer (Django Views)
- Data Access Layer (Django ORM)
- Database Layer (SQLite)

### 3.2 Project Structure
```
fintrack/
├── accounts/           # Authentication module
├── dashboard/          # Core features (income, budgets, subscriptions, savings)
├── expenses/           # Expense tracking module
├── fintrack/           # Project configuration
├── static/             # CSS, JS, images
├── templates/          # Global templates
├── media/              # User uploads (avatars)
├── manage.py
└── requirements.txt
```

### 3.3 Database Schema (ER Diagram)
[INSERT: ER diagram showing all models and relationships]

**Models:**
- User (Django built-in)
- UserProfile
- Expense
- Income
- CustomCategory
- CategoryBudget
- Subscription
- SavingsGoal
- SavingsContribution

---

## SECTION 4: MODULE-WISE FLOW WI   TH SCREENSHOTS

### 4.1 AUTHENTICATION MODULE

#### Flow Diagram
```
Landing Page → Register → Login → Dashboard
                    ↓
              Change Password
```

#### Screenshots Required:
1. **Landing Page** (`/`)
   - Screenshot showing welcome page with Register/Login buttons
   - Caption: "Landing page for unauthenticated users"

2. **Registration Page** (`/accounts/register/`)
   - Screenshot of registration form (username, email, password fields)
   - Caption: "User registration with email and password validation"

3. **Login Page** (`/accounts/login/`)
   - Screenshot of login form
   - Caption: "User authentication page"

4. **Change Password** (`/accounts/change-password/`)
   - Screenshot of password change form
   - Caption: "Password reset functionality"

#### Code Files:
```python
# accounts/models.py
# (No custom models - uses Django's built-in User)

# accounts/forms.py
[PASTE COMPLETE CODE]

# accounts/views.py
[PASTE COMPLETE CODE]

# accounts/urls.py
[PASTE COMPLETE CODE]

# accounts/templates/accounts/auth.html
[PASTE COMPLETE CODE]
```

---

### 4.2 DASHBOARD MODULE

#### Flow Diagram
```
Dashboard → View Stats → Filter by Date/Category
    ↓
Financial Health Score
    ↓
Charts (Category Breakdown, Daily Spending)
    ↓
Budget Alerts (if over 80%)
    ↓
Spending Forecast (current month)
```

#### Screenshots Required:
1. **Main Dashboard** (`/dashboard/`)
   - Full page screenshot showing:
     - Month navigation
     - 4 stat cards (Income, Spent, Balance, Savings Rate)
     - Financial Health card
     - Daily spending chart
     - Category donut chart
     - Top 5 categories
     - Recent transactions
   - Caption: "Main dashboard with analytics and visualizations"

2. **Dashboard with Filters Applied**
   - Screenshot showing custom date range filter
   - Caption: "Dashboard filtered by custom date range"

3. **Budget Alerts Banner**
   - Screenshot showing alert when category exceeds 80%
   - Caption: "Real-time budget alerts on dashboard"

4. **Spending Forecast Card**
   - Screenshot of forecast section (only visible for current month)
   - Caption: "AI-powered spending forecast based on daily average"

5. **Empty State**
   - Screenshot when no expenses exist
   - Caption: "Empty state with call-to-action for new users"

6. **Dark Mode Dashboard**
   - Screenshot of dashboard in dark theme
   - Caption: "Dark mode support across all pages"

#### Code Files:
```python
# dashboard/models.py
[PASTE COMPLETE CODE]

# dashboard/views.py - dashboard_view function
[PASTE COMPLETE CODE]

# dashboard/urls.py
[PASTE COMPLETE CODE]

# dashboard/templates/dashboard/dashboard.html
[PASTE COMPLETE CODE]
```

---

### 4.3 EXPENSE TRACKING MODULE

#### Flow Diagram
```
Expense List → Add Expense → Edit Expense → Delete Expense
    ↓              ↓
Filter by:    Category Warning
- Month/Year  (if Savings/Subscription)
- Search
- Category
- Date Range
    ↓
Bulk Delete
```

#### Screenshots Required:
1. **Expense List** (`/expenses/`)
   - Screenshot showing table with all expenses
   - Month navigation, search bar, category filter
   - Caption: "Expense list with advanced filtering options"

2. **Add Expense Form** (`/expenses/add/`)
   - Screenshot of expense creation form
   - Caption: "Add new expense with category selection"

3. **Category Warning**
   - Screenshot showing inline warning when selecting "Savings" or "Subscription"
   - Caption: "Smart category warnings guide users to correct features"

4. **Edit Expense** (`/expenses/<id>/edit/`)
   - Screenshot of edit form with pre-filled data
   - Caption: "Edit existing expense"

5. **Delete Confirmation** (`/expenses/<id>/delete/`)
   - Screenshot of delete confirmation page
   - Caption: "Confirmation before deleting expense"

6. **Bulk Delete**
   - Screenshot showing checkboxes selected with bulk delete button
   - Caption: "Bulk delete multiple expenses at once"

#### Code Files:
```python
# expenses/models.py
[PASTE COMPLETE CODE]

# expenses/forms.py
[PASTE COMPLETE CODE]

# expenses/views.py
[PASTE COMPLETE CODE]

# expenses/urls.py
[PASTE COMPLETE CODE]

# expenses/templates/expenses/expense_list.html
[PASTE COMPLETE CODE]

# expenses/templates/expenses/expense_form.html
[PASTE COMPLETE CODE]

# expenses/templates/expenses/expense_confirm_delete.html
[PASTE COMPLETE CODE]
```

---

### 4.4 SETTINGS MODULE

#### Flow Diagram
```
Settings → Income Management
        → Custom Categories
        → Budget Limits (per month)
        → CSV Upload
```

#### 4.4.1 Income Management

**Screenshots:**
1. **Income List** (`/settings/income/`)
   - Screenshot showing income entries table with filters
   - Caption: "Income tracking with source categorization"

2. **Add Income Modal**
   - Screenshot of add income form
   - Caption: "Add income entry with date, source, and amount"

**Code:**
```python
# dashboard/views.py - settings_income, income_add, income_edit, income_delete
[PASTE RELEVANT FUNCTIONS]
```

#### 4.4.2 Custom Categories

**Screenshots:**
1. **Categories Page** (`/settings/categories/`)
   - Screenshot showing default and custom category chips
   - Caption: "Manage custom expense categories"

**Code:**
```python
# dashboard/views.py - settings_categories
[PASTE COMPLETE FUNCTION]
```

#### 4.4.3 Budget Limits

**Screenshots:**
1. **Budget Settings** (`/settings/budget/`)
   - Screenshot showing budget cards for each category
   - Month navigation
   - "Copy Last Month" button
   - Caption: "Set monthly spending limits per category"

2. **Budget Card States**
   - Screenshot showing OK (green), Warning (amber), Danger (red) states
   - Caption: "Visual budget status indicators"

3. **Copy from Last Month**
   - Screenshot after clicking copy button with success toast
   - Caption: "One-click budget copying from previous month"

**Code:**
```python
# dashboard/views.py - settings_budget, budget_copy_last_month
[PASTE COMPLETE FUNCTIONS]
```

#### 4.4.4 CSV Upload

**Screenshots:**
1. **Upload Page** (`/settings/upload/`)
   - Screenshot of CSV upload form with format guide
   - Caption: "Bulk import expenses via CSV"

2. **Preview Step**
   - Screenshot showing first 5 rows preview
   - Caption: "Preview data before importing"

3. **Import Success**
   - Screenshot with success message showing count
   - Caption: "Successful bulk import confirmation"

**Code:**
```python
# dashboard/views.py - settings_upload
[PASTE COMPLETE FUNCTION]
```

---

### 4.5 SUBSCRIPTIONS MODULE

#### Flow Diagram
```
Subscriptions List → Add Subscription → Auto-billing on due date
    ↓                      ↓
Summary Stats      Edit/Delete/Pause
(Monthly/Yearly)          ↓
    ↓              Creates Expense automatically
Due Soon Alerts
```

#### Screenshots Required:
1. **Subscriptions Page** (`/subscriptions/`)
   - Screenshot showing subscription cards
   - Summary stats at top (monthly cost, yearly cost, active count, upcoming)
   - Caption: "Track recurring subscriptions with auto-billing"

2. **Add Subscription Modal**
   - Screenshot of add form with cycle options (weekly/monthly/yearly)
   - Caption: "Add new subscription with billing cycle"

3. **Due Soon Highlighting**
   - Screenshot showing subscriptions due within 7 days highlighted
   - Caption: "Visual alerts for upcoming billing dates"

4. **Subscription States**
   - Screenshot showing active, paused, and cancelled subscriptions
   - Caption: "Manage subscription lifecycle"

#### Code Files:
```python
# dashboard/models.py - Subscription model with advance_billing_date method
[PASTE SUBSCRIPTION MODEL]

# dashboard/views.py - subscriptions, subscription_add, subscription_edit, subscription_delete
[PASTE COMPLETE FUNCTIONS]

# dashboard/templates/dashboard/subscriptions.html
[PASTE COMPLETE CODE]
```

---

### 4.6 SAVINGS GOALS MODULE

#### Flow Diagram
```
Savings Goals List → Create Goal → Goal Detail Page
    ↓                    ↓              ↓
Total Saved      Icon Picker    Add Funds → Creates Expense
    ↓                    ↓              ↓
Progress Bars    Target Date    Contribution History
```

#### Screenshots Required:
1. **Savings Goals Page** (`/savings-goals/`)
   - Screenshot showing goal cards with progress bars
   - Caption: "Track multiple savings goals with visual progress"

2. **Add Goal Modal with Icon Picker**
   - Screenshot showing preset icon grid + custom icon input
   - Caption: "Create goal with custom icon selection"

3. **Goal Detail Page** (`/savings-goals/<id>/`)
   - Screenshot showing:
     - Progress ring
     - Stats (target, saved, remaining)
     - Deposit form
     - Contribution timeline
   - Caption: "Detailed goal view with contribution history"

4. **Add Funds**
   - Screenshot of deposit form
   - Caption: "Deposit funds to goal (creates expense automatically)"

#### Code Files:
```python
# dashboard/models.py - SavingsGoal, SavingsContribution
[PASTE MODELS]

# dashboard/views.py - savings_goals, savings_goal_add, savings_goal_detail, savings_goal_add_funds, etc.
[PASTE COMPLETE FUNCTIONS]

# dashboard/templates/dashboard/savings_goals.html
[PASTE COMPLETE CODE]

# dashboard/templates/dashboard/savings_goal_detail.html
[PASTE COMPLETE CODE]
```

---

### 4.7 PROFILE MODULE

#### Flow Diagram
```
Profile Page → Edit Name/Email → Upload Avatar → Export Data
                                      ↓
                                Remove Avatar
```

#### Screenshots Required:
1. **Profile Page** (`/profile/`)
   - Screenshot showing avatar, user info, edit form
   - Caption: "User profile management"

2. **Avatar Upload**
   - Screenshot after uploading avatar
   - Caption: "Custom profile picture upload"

3. **Export Data Link**
   - Screenshot showing link to export page
   - Caption: "Quick access to data export"

#### Code Files:
```python
# dashboard/views.py - profile
[PASTE COMPLETE FUNCTION]

# dashboard/templates/dashboard/profile.html
[PASTE COMPLETE CODE]
```

---

### 4.8 EXPORT DATA MODULE

#### Flow Diagram
```
Export Page → Select Filter Mode → Select Data Types → Select Categories → Download CSV
    ↓
Custom Range / Month-Year / Full Year
```

#### Screenshots Required:
1. **Export Page** (`/export-data/`)
   - Screenshot showing all filter options
   - Caption: "Advanced data export with multiple filter modes"

2. **Filter Modes**
   - Screenshot showing 3 radio options (Custom Range, Month/Year, Full Year)
   - Caption: "Flexible date filtering for exports"

3. **Downloaded CSV**
   - Screenshot of CSV opened in Excel showing UTF-8 BOM support
   - Caption: "Excel-compatible CSV export with proper encoding"

#### Code Files:
```python
# dashboard/views.py - export_data
[PASTE COMPLETE FUNCTION]

# dashboard/templates/dashboard/export.html
[PASTE COMPLETE CODE]
```

---

### 4.9 ADMIN PANEL MODULE

#### Flow Diagram
```
Admin Login → User List → Select User → View All User Data (Inlines)
    ↓              ↓
Actions:    Inlines:
- Activate  - Profile
- Deactivate- Income
            - Expenses
            - Budgets
            - Subscriptions
            - Savings Goals
            - Custom Categories
```

#### Screenshots Required:
1. **Admin Login** (`/admin/`)
   - Screenshot of Django admin login
   - Caption: "Admin panel authentication"

2. **User List**
   - Screenshot showing user list with date_joined, last_login, is_active
   - Caption: "User management dashboard"

3. **User Detail with Inlines**
   - Screenshot showing all inlines on one page
   - Caption: "Comprehensive user data view with inline editing"

4. **Activate/Deactivate Actions**
   - Screenshot showing bulk actions dropdown
   - Caption: "Bulk user management actions"

#### Code Files:
```python
# dashboard/admin.py
[PASTE COMPLETE CODE]

# expenses/admin.py
[PASTE COMPLETE CODE]
```

---

### 4.10 PRODUCT TOUR (ONBOARDING)

#### Flow Diagram
```
First Login → Tour Overlay → 5 Steps → Complete → Mark onboarding_complete=True
```

#### Screenshots Required:
1. **Tour Step 1** - Stats cards
2. **Tour Step 2** - Filter controls
3. **Tour Step 3** - Expenses link
4. **Tour Step 4** - Savings goals link
5. **Tour Step 5** - Theme toggle

Caption for all: "Interactive product tour for new users"

#### Code Files:
```python
# dashboard/views.py - tour_complete
[PASTE FUNCTION]

# dashboard/templates/dashboard/dashboard.html - Tour script section
[PASTE TOUR JAVASCRIPT]
```

---

## SECTION 5: COMPLETE CODE LISTING

### 5.1 Project Configuration
```python
# fintrack/settings.py
[PASTE COMPLETE FILE]

# fintrack/urls.py
[PASTE COMPLETE FILE]

# fintrack/wsgi.py
[PASTE COMPLETE FILE]

# fintrack/asgi.py
[PASTE COMPLETE FILE]

# manage.py
[PASTE COMPLETE FILE]
```

### 5.2 Accounts App
[All files already listed in Section 4.1]

### 5.3 Expenses App
[All files already listed in Section 4.3]

### 5.4 Dashboard App
[All files already listed in Sections 4.2, 4.4, 4.5, 4.6, 4.7, 4.8]

### 5.5 Templates
```html
# templates/base.html
[PASTE COMPLETE FILE]

# templates/navbar.html
[PASTE COMPLETE FILE]

# templates/footer.html
[PASTE COMPLETE FILE]

# templates/landing.html
[PASTE COMPLETE FILE]
```

### 5.6 Static Files
```css
# static/css/styles.css
[PASTE COMPLETE FILE - This will be very long, ~5000 lines]
```

```javascript
# static/js/filters.js
[PASTE COMPLETE FILE]
```

### 5.7 Requirements
```
# requirements.txt
Django==6.0.2
Pillow==11.1.0
python-dateutil==2.9.0
```

---

## SECTION 6: DATABASE DESIGN

### 6.1 Models Documentation

#### User (Django Built-in)
- username: CharField
- email: EmailField
- password: CharField (hashed)
- first_name: CharField
- last_name: CharField
- is_active: BooleanField
- date_joined: DateTimeField

#### UserProfile
- user: OneToOneField(User)
- avatar: ImageField
- onboarding_complete: BooleanField

#### Expense
- user: ForeignKey(User)
- title: CharField
- category: CharField
- amount: DecimalField
- date: DateField

#### Income
- user: ForeignKey(User)
- date: DateField
- source: CharField (choices)
- description: CharField
- amount: DecimalField

#### CustomCategory
- user: ForeignKey(User)
- name: CharField

#### CategoryBudget
- user: ForeignKey(User)
- category: CharField
- limit: DecimalField
- month: PositiveSmallIntegerField
- year: PositiveSmallIntegerField
- Unique together: (user, category, month, year)

#### Subscription
- user: ForeignKey(User)
- name: CharField
- amount: DecimalField
- cycle: CharField (weekly/monthly/yearly)
- category: CharField
- next_billing: DateField
- status: CharField (active/paused/cancelled)
- Methods: monthly_cost property, advance_billing_date()

#### SavingsGoal
- user: ForeignKey(User)
- name: CharField
- target: DecimalField
- saved: DecimalField
- target_date: DateField
- icon: CharField
- created_at: DateTimeField
- Properties: progress_pct, remaining

#### SavingsContribution
- goal: ForeignKey(SavingsGoal)
- amount: DecimalField
- date: DateField

### 6.2 Relationships
- User → UserProfile (One-to-One)
- User → Expense (One-to-Many)
- User → Income (One-to-Many)
- User → CustomCategory (One-to-Many)
- User → CategoryBudget (One-to-Many)
- User → Subscription (One-to-Many)
- User → SavingsGoal (One-to-Many)
- SavingsGoal → SavingsContribution (One-to-Many)

---

## SECTION 7: KEY FEATURES EXPLANATION

### 7.1 Authentication & Authorization
- Django's built-in authentication system
- Password hashing with PBKDF2
- Session-based authentication
- Login required decorators on all views
- User-scoped data (every query filters by request.user)

### 7.2 Dashboard Analytics
- Real-time aggregation queries
- Financial health score calculation
- Savings rate comparison with previous month
- Chart.js visualizations (doughnut, bar charts)
- Spending forecast using daily average projection

### 7.3 Budget Management
- Per-category monthly limits
- Real-time progress tracking
- Visual status indicators (OK/Warning/Danger)
- Budget alerts on dashboard
- Copy limits from previous month

### 7.4 Subscription Auto-billing
- Automatic expense creation on billing date
- `advance_billing_date()` method using dateutil.relativedelta
- Cycle normalization (weekly/yearly → monthly cost)
- Due-soon alerts (within 7 days)

### 7.5 Savings Goals
- Progress tracking with percentage calculation
- Contribution history timeline
- Automatic expense creation on deposit
- Icon customization (preset + custom Bootstrap Icons)

### 7.6 Data Export
- UTF-8 BOM for Excel compatibility
- Three filter modes (Custom Range, Month/Year, Full Year)
- Multi-select data types and categories
- CSV format with section headers

### 7.7 Dark Mode
- CSS custom properties for theming
- localStorage persistence
- Full coverage across all components
- Smooth transitions

### 7.8 Mobile Responsiveness
- Breakpoints at 991px, 768px, 480px
- Touch targets ≥44px
- Horizontal scroll on tables
- Stacked layouts on small screens

---

## SECTION 8: TESTING

### 8.1 Manual Testing Checklist
- [ ] User registration with validation
- [ ] Login/logout functionality
- [ ] Password change
- [ ] Add/edit/delete expense
- [ ] Bulk delete expenses
- [ ] Filter expenses by date/category
- [ ] Add/edit/delete income
- [ ] Create custom category
- [ ] Set budget limits
- [ ] Copy budget from last month
- [ ] Add/edit/delete subscription
- [ ] Subscription auto-billing
- [ ] Create savings goal
- [ ] Add funds to goal
- [ ] CSV upload (preview + import)
- [ ] Data export with filters
- [ ] Profile edit and avatar upload
- [ ] Dark mode toggle
- [ ] Product tour completion
- [ ] Admin panel user management
- [ ] Mobile responsiveness

### 8.2 Test Cases (Sample)

**Test Case 1: User Registration**
- Input: Valid username, email, matching passwords
- Expected: User created, redirected to dashboard, success toast
- Actual: [Pass/Fail]

**Test Case 2: Budget Alert**
- Input: Spend 85% of category budget
- Expected: Warning alert appears on dashboard
- Actual: [Pass/Fail]

**Test Case 3: Subscription Auto-billing**
- Input: Subscription with next_billing = yesterday
- Expected: Expense created automatically, next_billing advanced
- Actual: [Pass/Fail]

[Add more test cases as needed]

---

## SECTION 9: CHALLENGES & SOLUTIONS

### Challenge 1: Subscription Auto-billing Logic
**Problem:** How to automatically create expenses when billing date passes?
**Solution:** Implemented `advance_billing_date()` method that runs on page load, creates expenses for all elapsed cycles using `dateutil.relativedelta` for accurate date arithmetic.

### Challenge 2: Budget Alerts Performance
**Problem:** Computing budget status for every category on every dashboard load.
**Solution:** Only compute for current month (not custom ranges), use single aggregation query with `values().annotate()`.

### Challenge 3: CSV Export Excel Compatibility
**Problem:** Excel showing garbled characters for rupee symbol.
**Solution:** Added UTF-8 BOM (`\ufeff`) at start of CSV file.

### Challenge 4: Dark Mode Consistency
**Problem:** Maintaining color consistency across 50+ components.
**Solution:** Used CSS custom properties (`--bg`, `--text`, etc.) with single `[data-theme="dark"]` override block.

### Challenge 5: Empty State UX
**Problem:** Charts breaking when no data exists.
**Solution:** Added conditional rendering with dedicated empty state component showing call-to-action.

---

## SECTION 10: FUTURE ENHANCEMENTS

1. **Email Notifications**
   - Budget exceeded alerts
   - Subscription due reminders
   - Weekly spending summary

2. **Recurring Expense Templates**
   - Save common expenses as templates
   - One-click apply to current month

3. **Multi-currency Support**
   - Currency selection per user
   - Exchange rate API integration

4. **Bank Integration**
   - Plaid/Open Banking API
   - Auto-import transactions

5. **Mobile App**
   - React Native or Flutter
   - Push notifications

6. **Advanced Analytics**
   - Spending trends over time
   - Category comparison charts
   - Predictive budgeting

7. **Shared Budgets**
   - Household/family accounts
   - Split expenses

8. **PDF Reports**
   - Monthly summary PDF
   - Printable statements

---

## SECTION 11: CONCLUSION

FinTrack successfully demonstrates a full-stack web application with comprehensive personal finance management features. The project showcases proficiency in Django framework, database design, RESTful architecture, responsive UI design, and modern web development practices.

**Key Achievements:**
- 9 fully functional modules
- 30+ database models and views
- Mobile-responsive design
- Dark mode support
- Real-time analytics
- Data import/export
- Admin panel
- Production-ready code structure

**Learning Outcomes:**
- Django MVT architecture
- ORM and database relationships
- Session management
- Form validation
- Chart.js integration
- CSS theming with custom properties
- Responsive design principles
- User experience design

---

## SECTION 12: REFERENCES

1. Django Documentation - https://docs.djangoproject.com/
2. Bootstrap 5 Documentation - https://getbootstrap.com/docs/5.3/
3. Chart.js Documentation - https://www.chartjs.org/docs/
4. Python dateutil - https://dateutil.readthedocs.io/
5. MDN Web Docs - https://developer.mozilla.org/
6. Stack Overflow - https://stackoverflow.com/

---

## APPENDIX

### A. Installation Guide
```bash
# Clone repository
git clone <repository-url>
cd fintrack

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run migrations
python manage.py makemigrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser

# Run development server
python manage.py runserver

# Access application
# http://127.0.0.1:8000/
```

### B. Deployment Checklist
- [ ] Set DEBUG = False
- [ ] Configure ALLOWED_HOSTS
- [ ] Use environment variables for SECRET_KEY
- [ ] Set up PostgreSQL/MySQL (replace SQLite)
- [ ] Configure static files serving (WhiteNoise/Nginx)
- [ ] Set up media files storage (S3/CloudFront)
- [ ] Enable HTTPS
- [ ] Configure email backend
- [ ] Set up logging
- [ ] Add monitoring (Sentry)

### C. Git Commit History
[Include major commits with descriptions]

### D. Team Contributions
[If group project, list individual contributions]

---

## FORMATTING GUIDELINES FOR WORD DOCUMENT

1. **Fonts:**
   - Headings: Arial Bold, 14-16pt
   - Body: Arial, 11pt
   - Code: Consolas/Courier New, 9pt

2. **Spacing:**
   - Line spacing: 1.15
   - Before paragraph: 6pt
   - After paragraph: 6pt

3. **Page Setup:**
   - Margins: 1 inch all sides
   - Page numbers: Bottom center
   - Header: Project name + your name

4. **Code Blocks:**
   - Use table with light gray background
   - Border: 1pt solid gray
   - Syntax highlighting (if possible)

5. **Screenshots:**
   - High resolution (1920x1080 or higher)
   - Add border (1pt black)
   - Caption below each image
   - Number all figures (Figure 1, Figure 2, etc.)

6. **Tables:**
   - Header row: Bold, light blue background
   - Alternate row shading for readability

---

## ESTIMATED PAGE COUNT

- Section 1-3: 10 pages
- Section 4 (Screenshots + Code): 150-200 pages
- Section 5 (Complete Code): 100-150 pages
- Section 6-12: 30 pages

**Total: 290-390 pages**

---

## TIPS FOR CREATING THE DOCUMENT

1. **Take screenshots systematically:**
   - Use consistent browser window size
   - Clear browser cache for clean UI
   - Use dummy data that looks realistic
   - Capture both light and dark modes

2. **Code formatting:**
   - Use syntax highlighter (Pygments, highlight.js)
   - Add line numbers
   - Keep indentation consistent
   - Add comments explaining complex logic

3. **Proofread:**
   - Check all code for typos
   - Verify all screenshots are clear
   - Ensure consistent terminology
   - Run spell check

4. **Create Table of Contents:**
   - Use Word's automatic TOC feature
   - Update before final submission

5. **Add page breaks:**
   - Start each major section on new page
   - Don't split screenshots across pages

---

This guide provides the complete structure. You now need to:
1. Take all the screenshots as listed
2. Copy-paste all code files into the document
3. Format according to guidelines
4. Add your personal details
5. Proofread and submit

# Jira Service Management - Sales Performance Dashboard

A powerful, interactive dashboard for analyzing Jira Service Management sales data with advanced filtering, sorting, and visualization capabilities. Track sales performance, presales activities, technical support workload, and project due dates in real-time.

![Dashboard Preview](https://img.shields.io/badge/Status-Active-success)
![License](https://img.shields.io/badge/License-MIT-blue)

## 📸 Screenshot

![Dashboard Screenshot](screenshot.png)

## ✨ Features

### 📊 Multi-Tab Analytics
- **💰 Sales Statistics**: Track sales team performance with individual KPI settings (default KPI: 5)
- **💡 Presales Statistics**: Monitor presales team workload with KPI support (default KPI: 8)
- **🛠️ Technical Support Statistics**: Track technical support team workload with KPI support (default KPI: 8)
- **📅 Due Date Summary**: View upcoming deadlines with customizable time range (1-24 months, default: 3 months)
- **📈 KPI Charts**: Interactive visual analytics with 5 dynamic charts for performance tracking

### 🎯 Key Capabilities
- **Customizable KPIs**: Set individual or global KPI targets for each team member within their respective tabs
- **Separated Filtering**: Dedicated Team dropdown + Name search box for precise filtering
- **Advanced Sorting**: Click column headers to sort data across all tables
- **Real-time Statistics**: Dynamic stat cards showing filtered vs. total data
- **Revenue Tracking**: Monitor expected and recognized revenue with realization rates (Sales tab)
- **Progress Visualization**: Color-coded completion bars and achievement rates
- **Data Persistence**: KPI settings saved to browser localStorage
- **Flexible Date Range**: Adjust Due Date Summary to show 1-24 months of upcoming deadlines
- **Mobile Responsive**: Optimized layout for phones and tablets
- **Interactive Tooltips**: Context-sensitive help icons (ℹ) next to each tab title explaining tab purposes, usage, and features with auto-wrapping text display

### 📥 Export Options
- **PDF Export**: Download current view with applied filters (print-friendly)
- **Excel Export**: Export all data to a multi-sheet workbook
  - Sheet 1: Sales Statistics
  - Sheet 2: Presales Statistics
  - Sheet 3: Technical Support Statistics
  - Sheet 4: Due Date Summary (reflects your Display Months setting)
- **HTML Export**: Generate professional complete report
  - Executive Summary with key metrics
  - All 4 sections with full data (no pagination)
  - Sales/Presales/TS tables sorted by Achievement Rate (highest first)
  - Due Date Summary reflects your Display Months setting
  - Suitable for management presentations

## 🚀 Quick Start

### 1. Download
Simply download `index.html` - it's a standalone file with no dependencies!

### 2. Open
Open the HTML file in any modern web browser (Chrome, Firefox, Edge, Safari).

**Or use GitHub Pages**: https://whfan0827.github.io/jsm-sales-performance-dashboard/

### 3. Upload CSV
Click "Upload CSV" and select your Jira Service Management export CSV file.

### 4. Analyze
Switch between tabs, set KPIs, apply filters, and export reports!

## 📋 CSV Format

The dashboard expects a Jira Service Management CSV export with the following columns:

### Required Columns
- `Issue key` - Jira issue identifier
- `Issue id` - Issue ID
- `Summary` - Issue description
- `Status` - Current status (e.g., Done, 3-Design, 5-Build)
- `Custom field (MMPJ_MCI_Sales)` - Sales person name
- `Custom field (MMPJ_MCI_SalesTeamID)` - Sales team ID
- `Custom field (MMPJ_MCI_funding(num))` - Expected revenue/funding amount
- `Due date` - Issue due date

### Optional Columns
- `Custom field (MMPJ_MCI_PS)` - Presales personnel (supports multiple values and columns)
  - Also reads: PS1, PS2, PS3, PS4 (5 columns total with deduplication)
- `Custom field (MMPJ_MCI_TS)` - Technical Support personnel (supports multiple values and columns)
  - Also reads: TS1, TS2 (3 columns total with deduplication)
- Additional custom fields as needed

See `sample.csv` for a complete example.

## 🎨 Status Classification

The dashboard automatically classifies Jira Service Management statuses into four categories:

- **ToDo** (Yellow): Status starting with 0, 1, 2, or "To Do"
- **InProgress** (Blue): Status starting with 3-8
- **Under Review** (Purple): Status 9.1-Success or 9.2-Project Report Status
- **Done** (Red): Status is "Done"

Other 9.x statuses (not 9.1 or 9.2) are classified as InProgress.

## 👥 Multi-Personnel Support

The dashboard supports multiple personnel assignments for Presales and Technical Support:

- **Sales**: Single assignment per case
- **Presales**: Supports multiple personnel per case across 5 columns (PS, PS1, PS2, PS3, PS4)
  - Cases are counted for each assigned person
  - Automatic deduplication if same person appears in multiple columns
- **Technical Support**: Supports multiple personnel per case across 3 columns (TS, TS1, TS2)
  - Cases are counted for each assigned person
  - Automatic deduplication if same person appears in multiple columns

This allows accurate workload tracking when multiple team members collaborate on the same case.

## 💡 Usage Tips

### Understanding Tabs
Hover over the ℹ icon next to each tab title to see detailed information about:
- **💰 Sales Statistics**: Revenue tracking, KPI settings, and team performance metrics
- **💡 Presales Statistics**: Workload monitoring with multi-personnel support
- **🛠️ Technical Support Statistics**: Support team workload and completion tracking
- **📅 Due Date Summary**: Project deadline overview with customizable time ranges
- **📈 KPI Charts**: Visual analytics dashboard with interactive charts
  - Team Performance: Case count and revenue by team
  - Sales Ranking: Top 10 sales by revenue
  - Presales Performance: Top 10 PS by case count and completion rate
  - Technical Support Performance: Top 10 TS by case count and completion rate
  - Cumulative Due Date Trend: Full-width stacked bar + line chart showing cumulative cases over all months
  - Click on chart elements to drill down to detailed data

### Setting KPIs
1. **Individual KPI**: Click the number in the "KPI Target" column for any person
2. **Tab-Specific Global KPI**: Each tab (Sales, Presales, Technical Support) has its own KPI setting
   - Sales default: 5 cases/person
   - Presales default: 8 cases/person
   - Technical Support default: 8 cases/person
3. **Apply to All**: Use the KPI input in each tab and click "Apply to All" to set the same KPI for all team members in that tab

### Filtering Data (Sales Tab)
- **Team Filter**: Select a specific team from the dropdown (e.g., "C", "N22", "SS") or choose "All Teams"
- **Name Search**: Type to search sales person names (fuzzy match)
- **Combined Filtering**: Both filters work together - select Team C + search "Allen" to find specific person
- **Sorting**: Click column headers to sort ascending/descending
- **Page Size**: Adjust "Show" dropdown to change number of rows displayed

### Exporting Reports
- **PDF**: Exports only the currently visible tab with current filters applied
- **Excel**: Exports all data from all five tabs (Sales, Presales, Technical Support, Due Date Summary, KPI Charts data)
- **HTML**: Generates a professional complete report with:
  - Executive Summary section with aggregated metrics
  - KPI Charts section with 5 visual charts (Team, Sales, PS, TS, Cumulative Due Date Trend)
  - All personnel from Sales/Presales/Technical Support (no pagination)
  - Data sorted by Achievement Rate for easy performance review
  - Due Date Summary with your selected month range
  - Print-optimized formatting for management presentations

## 📱 Mobile Support

Fully responsive design optimized for:
- 📱 Smartphones (portrait & landscape)
- 📱 Tablets
- 💻 Desktop browsers

Features on mobile:
- Touch-friendly horizontal scrolling for wide tables
- Optimized font sizes and spacing
- Stacked layout for controls and cards
- Tab buttons wrap automatically

## 🔧 Browser Compatibility

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Edge 90+
- ✅ Safari 14+
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

## 📊 Sample Data

Use `sample.csv` to test the dashboard features:

```bash
# Simply upload sample.csv to see the dashboard in action
# Contains 15 sample projects with realistic data
```

## 🛠️ Technical Details

### Technologies Used
- Pure HTML/CSS/JavaScript (no framework dependencies)
- [Chart.js 4.4.0](https://www.chartjs.org/) for interactive data visualization
- [SheetJS](https://sheetjs.com/) for Excel export
- LocalStorage API for data persistence
- CSS Grid & Flexbox for responsive layout

### File Size
- HTML: ~175 KB (single file, includes all functionality)
- No external dependencies required at runtime
- Chart.js and SheetJS libraries loaded from CDN
- Fully self-contained with mobile-responsive CSS, intelligent tooltips, and interactive charts

### Recent Updates

#### v1.8 (Latest)
- **🔍 Under Review Status Support**: New status category for enhanced workflow tracking
  - **Smart Classification**: Automatically identifies cases in review stages (9.1-Success, 9.2-Project Report Status)
  - **Visual Distinction**: Purple theme (#a29bfe to #6c5ce7) for Under Review across all visualizations
  - **Complete Integration**: Under Review column added to all tables and charts
    - 💰 Sales Statistics: Under Review column with purple status card in dashboard
    - 💡 Presales Statistics: Full Under Review data tracking and sorting
    - 🛠️ Technical Support Statistics: Complete Under Review integration
    - 📅 Due Date Summary: Under Review tracking across all months
    - 📈 KPI Charts: PS and TS performance charts include Under Review data layer
  - **Accurate Metrics**: All completion rates and statistics now include Under Review cases
  - **Enhanced Sorting**: Updated all sort functions to support the new column
  - **Backward Compatible**: Maintains compatibility with existing data exports
- **Updated Status Classification**: Four categories (ToDo, InProgress, Under Review, Done)
- **Refined Logic**: Status 9.1 and 9.2 now classified as Under Review; other 9.x remain InProgress

#### v1.7
- **📊 Enhanced Team Performance Chart**: Added case count overlay to team performance visualization
  - **Dual Metrics Display**: Shows both revenue bars and case count line in single view
  - **Right Y-Axis**: Dedicated axis for case count with clear labeling
  - **Visual Clarity**: Blue line chart overlays revenue bars for easy comparison
  - **Comprehensive Insights**: Analyze team performance by both volume and value
- **Improved Chart Layout**: Better positioning and visual hierarchy for clearer data interpretation

#### v1.6
- **📄 Table Pagination System**: Enhanced data navigation for Sales, Presales, and Technical Support tables
  - **Previous/Next Navigation**: Browse through large datasets with intuitive pagination controls
  - **Page Information Display**: Shows current page, total pages, and item count (e.g., "Page 2 of 5 (43 items)")
  - **Smart Visibility**: Pagination controls auto-hide when viewing all data or single page
  - **Right-Aligned Layout**: Controls positioned on the right side for better visual flow
  - **Interactive Buttons**: Cursor changes to pointer on hover with visual feedback
  - **Auto-Reset**: Returns to page 1 when changing page size or applying filters
  - **Default Display**: Shows 10 items per page for optimal viewing
- **📊 Enhanced Project Type Chart**: Improved visualization and clarity
  - **Total Bars**: Added summary bars for each project type (AI-Total, Security-Total, Azure-Total)
  - **Visual Distinction**: Total bars highlighted with red borders for easy identification
  - **Comprehensive X-Axis Labels**: Shows both type and size (e.g., "AI-S", "Security-M", "Azure-L")
  - **Abbreviated Display**: Uses single letters for sizes (S/M/L) and "Security" for Information Security
  - **Clear Categorization**: Instantly identify which type and size each bar represents
- **📈 Chart Layer Optimization**: Improved visibility of completion rate trends
  - **Presales Performance**: Completion rate curve now displays above stacked bars
  - **Technical Support Performance**: Completion rate curve now displays above stacked bars
  - **Better Trend Visibility**: Line charts positioned on top layer for clearer analysis

#### v1.5
- **💼 Project Type Revenue Analysis Chart**: New 6th chart in KPI Charts tab
  - **Three-Category Classification**: Automatically categorizes all cases into AI, Information Security, or Azure
    - **AI**: Cases containing "[MCI-AI]" or "AI, Agents & Dev"
    - **Information Security**: Cases containing "[MCI-Security]" or "Microsoft Sentinel"
    - **Azure**: All other Azure services (AMM, Migration, VDI, etc.)
  - **Stacked Revenue Visualization**: Shows revenue breakdown by case status
    - Green (bottom) = Done Revenue (completed cases)
    - Orange (middle) = In Progress Revenue (active cases)
    - Blue (top) = To Do Revenue (pending cases)
  - **Case Count Line**: Purple line chart overlays case quantity for each type
  - **Enhanced Tooltip**: Displays comprehensive statistics
    - Total Revenue with status breakdown
    - Revenue Realization Rate (percentage of completed revenue)
    - Average revenue per case
    - Funding coverage (cases with/without funding amounts)
  - **Full-Width Layout**: Positioned below Cumulative Chart for optimal visibility
  - **Business Insights**: Enables quick assessment of revenue distribution and completion rates across project types
- **Optimized Tooltip Information**: Removed duplicate data entries from chart tooltips for cleaner, more focused display
- **Smart Data Classification**: Automatic project type detection based on Summary field keywords

#### v1.4
- **📊 Cumulative Due Date Trend Chart**: New 5th chart in KPI Charts tab
  - **Mixed Visualization**: Stacked bar chart + line chart showing cumulative due date case trends over time
  - **Comprehensive Time Range**: Displays ALL months present in your data (not limited by Due Date Summary settings)
  - **Stacked Bars**:
    - Green (bottom) = Cumulative Completed cases (status: Done)
    - Orange (top) = Cumulative Remaining cases (status: In Progress + To Do)
  - **Red Line**: Cumulative Total showing overall trend
  - **Enhanced Tooltip**: Shows monthly new cases count when hovering over data points
  - **Interactive**: Click anywhere on chart to jump to Due Date Summary tab for detailed breakdown
  - **Full-Width Layout**: Occupies entire row below the 2x2 chart grid for better visibility
  - **Independent Data Source**: Uses separate `allDueDateData` to ensure all historical months are displayed
- **Data Architecture Improvement**: Refactored `displayDueDateSummary()` to generate both limited (for table) and complete (for charts) datasets
- **Improved Terminology**: Changed "Pending" to "Remaining" for clearer understanding
- **Clear Documentation**: Enhanced info tooltip explaining calculation methodology for each dataset

#### v1.3
- **📈 KPI Charts Tab**: Brand new visual analytics dashboard
  - **Team Performance Chart**: Grouped bar chart showing case count and revenue (Expected/Recognized) by team with dual Y-axis
  - **Sales Ranking Chart**: Horizontal bar chart displaying Top 10 sales by revenue with interactive drill-down
  - **Presales Performance Chart**: Mixed chart (stacked bar + line) showing Top 10 PS workload with ToDo/InProgress/Done breakdown and completion rate
  - **Technical Support Performance Chart**: Mixed chart showing Top 10 TS workload with status breakdown and completion rate
  - Click on any chart element to jump to the corresponding tab with auto-filtering
- **Multi-Column Personnel Support**: Enhanced data processing for Presales and Technical Support
  - Presales: Reads 5 columns (PS, PS1, PS2, PS3, PS4) with automatic deduplication
  - Technical Support: Reads 3 columns (TS, TS1, TS2) with automatic deduplication
  - Prevents double-counting when same person appears in multiple columns
- **Enhanced HTML Export**: KPI Charts now included in downloadable reports
  - Charts rendered as high-quality PNG images in Executive Summary section
  - 2x2 responsive grid layout for professional presentations
- **Refreshed Icon Set**: Updated all tab icons for better visual distinction
  - 💰 Sales | 💡 Presales | 🛠️ Technical Support | 📅 Due Date | 📈 KPI Charts
- **Technology Stack**: Integrated Chart.js 4.4.0 for interactive data visualization

#### v1.2
- **Separated Filtering UI**: Team dropdown + Name search for Sales tab
  - Team filter uses exact match (select "C" shows only Team C members)
  - Name search uses fuzzy match (search "Chen" finds all people with "Chen" in name)
  - Both filters work together with AND logic for precise results
  - Compact layout: 150px Team dropdown + flexible Name search box
  - Responsive: horizontal on desktop, vertical stack on mobile
- Eliminates ambiguity when searching short strings like "C"

#### v1.1
- Enhanced tab tooltips with context-sensitive help
- Improved tooltip design with auto-wrapping for better readability
- Optimized mobile date parsing for broader browser compatibility

## 📝 Customization

### Modify Status Classification
Edit the `classifyStatus()` function in the HTML file:

```javascript
function classifyStatus(status) {
    if (!status) return null;

    const statusLower = status.toLowerCase();
    if (statusLower === 'done') return 'Done';

    // Check for Under Review statuses (9.1-Success, 9.2-Project Report Status)
    if (status.startsWith('9.1') || status.startsWith('9.2')) {
        return 'UnderReview';
    }

    const firstChar = status[0];
    if (['0', '1', '2'].includes(firstChar)) return 'ToDo';
    if (['3', '4', '5', '6', '7', '8'].includes(firstChar)) return 'InProgress';
    if (firstChar === '9') return 'InProgress'; // Other 9.x statuses

    return null;
}
```

### Change Color Scheme
Modify the `.stat-card` CSS classes to customize colors:

```css
.stat-card.todo {
    background: linear-gradient(135deg, #ffd93d 0%, #ffb700 100%);
}

.stat-card.underreview {
    background: linear-gradient(135deg, #a29bfe 0%, #6c5ce7 100%);
}
```

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

## 📄 License

MIT License - feel free to use this project for personal or commercial purposes.

## 🙏 Acknowledgments

Built with modern web standards and best practices for a smooth user experience.

---

**Note**: This dashboard processes all data locally in your browser. No data is sent to external servers, ensuring complete privacy and security.

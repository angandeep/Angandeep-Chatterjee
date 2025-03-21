\# Exploratory Testing Session - Monefy App (Android) -- Angandeep
Chatterjee

Results from a 2-hour exploratory testing session of the Monefy Android
app are documented below in tabular format.

1.  **Exploratory Testing Charters and Findings**:

  ---------------------------------------------------------------------------
  **Charter   **Goal**          **Findings**                 **Status**
  ID**                                                       
  ----------- ----------------- ---------------------------- ----------------
  1           Verify            \- Subscription activated    Partially
              Subscription and  (7-day plan). - Autopay      working with
              Autopay Flow      added, but page loads        bugs
                                slowly. - Brief UI delay     
                                (1s) shows subscription      
                                page, then home page with    
                                \$0. - **Bug:** \"No         
                                internet connection\" error  
                                despite working connection.  

  2           Test Expense and  \- Expenses added, but       Functional with
              Income Tracking   negative values not          limitations
                                allowed. - Total expenses    
                                can exceed income, showing   
                                negative balance. - Expense  
                                % calculation accurate. -    
                                **Bug:** No negative value   
                                support (e.g., -\$800        
                                reimbursement). - **Bug:**   
                                Sidebar \"Incomes\" option   
                                unresponsive.                

  3           Evaluate UI       \- Dark theme works. -       Partially
              Consistency and   **Bug:** Same interface for  working with UI
              Themes            day/week/month views (no     issue
                                time-specific graphs).       

  4           Assess Budget     \- Budget mode works. -      Functional but
              Mode              **Bug:** No warning when     missing feature
              Functionality     expenses near limit (e.g.,   
                                95%).                        
  ---------------------------------------------------------------------------

2.  **Prioritization of Charters:**

  ------------------------------------------------------------------------
  **Charter   **Priority**           **Reasoning**
  ID**                               
  ----------- ---------------------- -------------------------------------
  1           High                   Core feature; bugs affect payment and
                                     trust.

  2           High                   Critical functionality; bugs limit
                                     expense tracking.

  3           Medium                 UI issue impacts experience, not core
                                     function.

  4           Medium                 Usability flaw (no warning) but not
                                     critical.
  ------------------------------------------------------------------------

3.  **Risks to Mitigate:**

  -----------------------------------------------------------------------
  **Risk   **Description**
  ID**     
  -------- --------------------------------------------------------------
  1        Data accuracy issues from wrong errors or no negative expense
           support.

  2        User trust loss due to slow pages and unresponsive UI.

  3        Missing features (graphs, warnings) reduce competitiveness.

  4        Subscription flow bugs may disrupt payments and retention.
  -----------------------------------------------------------------------

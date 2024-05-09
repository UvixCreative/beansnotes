# All open issues
	- {{query (and (page-tags issue) (not (page-property issue-status Solved)) (not (page-property issue-status Closed)))}}
	  query-sort-by:: tags
	  query-table:: true
	  query-sort-desc:: true
-
- # All solved issues
	- {{query (and (page-tags issue) (or (page-property issue-status Closed) (page-property issue-status Solved) ))}}
- # Issue template
  template:: issue-template
  template-including-parent:: false
	- tags:: issue
	  issue-status:: New
	  solved-date::
	- # Problem
		-
	- # Research
		-
	- # Troubleshooting
		-
	- # Solution
		-
-
-
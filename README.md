github2jira
===========

A simple ruby script to port github issues into CSV format compatible with Jira importer.

Usage
-----

I usually do this from irb - change the required username and password values 
(look for instances of github_username and github_password) and do the following:

require 'export_issues'
ExportIssues.get_issues(<from>, <to>)

Where from and to represent the range of issues you want to retrieve. The retrieved values
(along with comments) are saved by default to a file called ghissues.csv

**WARNING**: Jira CSV importer has a habit of choking on the hash character (#) in weird places.
Either escape the char or replace it with something like "No. of XYZ" instead of "# of XYZ".
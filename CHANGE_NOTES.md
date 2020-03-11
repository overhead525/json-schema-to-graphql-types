The mapBasicAttrbuteType function now successfully processes arrays.
I would like to write some documentation that shows users that they must use the following syntax:

['null', 'string']

I have handled any errors that would come up from improper syntax, so they would eventually figure it out, but I'd like to be nice.

I have multiple test cases demonstrating the success of the altered function, and none of the original test cases have failed.

You may see errors from ESlint complaining about spaces in front of functions parentheses, but this is irrelevant to the issue.

# a11y-checker
# 1. Overall Purpose:
The Python script is designed to perform accessibility analysis on a given URL.
print("It uses multiple tools and techniques to identify potential accessibility issues on a web page.

print("\n")

# 2. Function Roles:

`run_lighthouse(url)`: This asynchronous function executes the Lighthouse command-line tool for the given URL.
It captures the output, which is in JSON format, and returns it.")
Lighthouse provides a comprehensive accessibility audit, including scores and specific issues like color contrast.


 `analyze_accessibility(url)`: This asynchronous function uses Playwright to launch a browser and navigate to the specified URL.
It injects the Axe-core library into the page and runs an accessibility scan using `axe.run()`.
It also performs basic keyboard accessibility checks by verifying focus visibility and checking if interactive elements are reachable by keyboard.
Finally, it calls `run_lighthouse` to get Lighthouse results and returns both Axe-core and Lighthouse findings.



`generate_html_report(violations, lighthouse_results, url)`: This asynchronous function takes the Axe-core violations and Lighthouse results as input.
It generates an HTML report file (`accessibility_report.html`) that summarizes the findings.
The report includes a table of Axe-core violations with details like description, impact, and HTML snippets, as well as the Lighthouse accessibility score and color contrast issues.

`get_real_life_impact(violation_description)`: This helper function provides example real-life impact descriptions for some common Axe-core violations.
It's used within `generate_html_report` to add a user-friendly explanation of the violation's effect.

print("\n")

`main()`: This asynchronous function serves as the entry point of the script.
It defines the URL to be analyzed (currently hardcoded) and calls `analyze_accessibility` to get the results.
If the analysis is successful, it then calls `generate_html_report` to create the HTML report.
It uses `asyncio` to run the asynchronous operations.


# 3. Key Libraries Used:
Key Libraries Used:
`asyncio`: Provides the infrastructure for writing concurrent code using async/await syntax. It's used to manage the asynchronous operations like browser interaction and running subprocesses.
`playwright`: An automation library for browsers. It's used here to launch a browser, navigate to the URL, inject Axe-core, and interact with the page for keyboard accessibility checks.
`json`: Used for working with JSON data, specifically for loading and parsing the JSON output from Axe-core and Lighthouse.
`bs4` (BeautifulSoup): Although imported, it is not actively used in the provided code snippet.
`requests`: Although imported, it is not actively used in the provided code snippet.
`subprocess`: Used to run external commands, specifically the Lighthouse command-line tool.

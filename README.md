# SDE-Intern-Technical-Screening-Solutions
SDE Intern – Technical Screening Solutions

Role: Software Development Engineer Intern (6 Months)
Candidate: Hari Krishna
Email: periketi.hari54@gmail.com

---

1. TypeScript

Question

Review the given TypeScript code and identify the exact line numbers that cause a runtime crash or a type error. Explain how to fix them.

Answer

Line 2 and Line 5 cause errors.

- Line 2: "user.age.toFixed(2)" causes a runtime error because "user" or "user.age" may be undefined. Use optional chaining or a default value.
- Line 5: "processUser()" causes a TypeScript error because the required user argument is missing. Pass a valid user object, such as "processUser({ name: "Hari", age: 21 })".

---

2. React

Question

Review the given React component and list the problems related to React behavior, TypeScript types, and error handling. Give a one-line fix for each.

Answer

Problems and Fixes:

- Line 2: Using "any" is not a good practice. Define a proper TypeScript interface for user data.
- Line 4: "useState()" has no proper data type. Use "useState<User | null>(null)".
- Line 5: There is no cleanup in "useEffect". Use "AbortController" to cancel old requests.
- Line 6: The user ID is directly added to the URL. Use "encodeURIComponent(userId)".
- Line 7: There is no HTTP error check. Check "res.ok" before converting the response to JSON.
- Line 8: API data is stored without validation. Validate the data before updating the state.
- Line 9: The callback may receive outdated data. Cancel previous requests when the user ID changes.
- Line 12: If "onFetch" changes on every render, repeated API calls may happen. Use "useCallback" in the parent component.
- Line 13: "user.name" has no defined TypeScript type. Define a User interface with a name property.
- Line 13: There is no error message when fetching fails. Add an error state.
- Line 13: Loading and error conditions are not handled separately. Add separate loading, success, and error states.

---

3. SQL

Question

Given the following tables:

homes

- id
- name

bills

- id
- home_id
- amount
- due_date
- paid_at

"paid_at" is NULL when the bill is unpaid.

Write one SQL query that returns each home's name and its total unpaid amount. Include only homes with more than 10000 unpaid. Sort by the highest total first.

Answer

SELECT
    h.name,
    SUM(b.amount) AS total_unpaid
FROM homes h
JOIN bills b
    ON h.id = b.home_id
WHERE b.paid_at IS NULL
GROUP BY h.id, h.name
HAVING SUM(b.amount) > 10000
ORDER BY total_unpaid DESC;


---

Conclusion

This repository contains my solutions to the TypeScript, React, and SQL technical screening questions for the Software Development Engineer Internship. The answers focus on identifying coding issues, improving error handling, understanding React behavior, and writing efficient SQL queries.

---

Author: Hari Krishna

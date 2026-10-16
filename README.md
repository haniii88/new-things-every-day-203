```javascript
function dailyLog203() {
  const passwords = [
    "hello123",
    "MySecure@2026",
    "abc",
    "JavaScript!42",
  ];

  function analyzePassword(password) {
    const checks = {
      length: password.length >= 12,
      uppercase: /[A-Z]/.test(password),
      lowercase: /[a-z]/.test(password),
      number: /[0-9]/.test(password),
      symbol: /[^A-Za-z0-9]/.test(password),
    };

    const score = Object.values(checks).filter(Boolean).length;

    const strength =
      score <= 2 ? "Weak" :
      score <= 4 ? "Moderate" : "Strong";

    return { strength, checks };
  }

  console.log("=== Password Strength Report ===");

  passwords.forEach((password, index) => {
    const result = analyzePassword(password);

    console.log(`Password ${index + 1}: ${result.strength}`);
    console.log(
      `Checks passed: ${
        Object.values(result.checks).filter(Boolean).length
      }/5`
    );
  });
}

dailyLog203();
```

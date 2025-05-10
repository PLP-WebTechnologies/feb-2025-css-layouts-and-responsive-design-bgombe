# CSS Layouts and Responsive Design

## Objectives

Implement Flexbox and Grid for layout design.
Make the webpage responsive using media queries.
Ensure proper alignment and spacing.

## Instructions

- use Flexbox or CSS Grid.
- Add a navigation bar and structure the content.
- Use media queries to adjust layout for mobile, tablet, and desktop.

>[!NOTE]
>  - Include at least:
>  - navigation bar
>  - media queries

# Tasks

- Apply Flexbox or Grid for layout.
- Make the page responsive.
- Test across different screen sizes.

Happy Coding! 💻✨


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Fill-in Form with Flexbox Layout</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 2rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
      background-color: #f5f5f5;
    }
    h1 {
      margin-bottom: 1rem;
    }
    form {
      display: flex;
      flex-direction: column;
      max-width: 400px;
      width: 100%;
      background: white;
      padding: 1.5rem;
      border-radius: 8px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      box-sizing: border-box;
    }
    label {
      margin-top: 1rem;
      font-weight: bold;
    }
    input, textarea {
      width: 100%;
      padding: 0.5rem;
      margin-top: 0.25rem;
      box-sizing: border-box;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 1rem;
      resize: vertical;
    }
    button {
      margin-top: 1.5rem;
      padding: 0.75rem;
      font-size: 1rem;
      background-color: #007BFF;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    button:hover {
      background-color: #0056b3;
    }
    #output {
      margin-top: 2rem;
      padding: 1rem;
      border: 1px solid #ccc;
      max-width: 400px;
      width: 100%;
      background-color: #fff;
      border-radius: 8px;
      box-sizing: border-box;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }

    /* Responsive adjustments */
    @media (max-width: 480px) {
      body {
        margin: 1rem;
      }
      form, #output {
        max-width: 100%;
        padding: 1rem;
      }
      button {
        font-size: 0.9rem;
        padding: 0.6rem;
      }
    }
  </style>
</head>
<body>
  <h1>Fill-in Form</h1>
  <form id="fillForm">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required />

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required />

    <label for="message">Message:</label>
    <textarea id="message" name="message" rows="4" required></textarea>

    <button type="submit">Submit</button>
  </form>

  <div id="output" aria-live="polite"></div>

  <script>
    const form = document.getElementById('fillForm');
    const output = document.getElementById('output');

    form.addEventListener('submit', function(event) {
      event.preventDefault();

      const formData = new FormData(form);
      const data = {};
      formData.forEach((value, key) => {
        data[key] = value;
      });

      output.innerHTML = '<h2>Submitted Data</h2>' +
        '<p><strong>Name:</strong> ' + data.name + '</p>' +
        '<p><strong>Email:</strong> ' + data.email + '</p>' +
        '<p><strong>Message:</strong> ' + data.message + '</p>';

      // Optionally, clear the form
      // form.reset();
    });
  </script>
</body>
</html>


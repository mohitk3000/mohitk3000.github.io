<style>
/* Dark mode toggle styles */
.theme-toggle {
  position: fixed;
  top: 20px;
  right: 20px;
  z-index: 1000;
}

.theme-toggle button {
  background: none;
  border: 2px solid #333;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  cursor: pointer;
  font-size: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
}

.theme-toggle button:hover {
  transform: scale(1.1);
}

/* Light mode styles */
body {
  background-color: #ffffff;
  color: #333333;
  transition: background-color 0.3s ease, color 0.3s ease;
}

body.dark-mode {
  background-color: #1a1a1a;
  color: #f0f0f0;
}

body.dark-mode a {
  color: #4a9eff;
}

body.dark-mode h1, body.dark-mode h2, body.dark-mode h3 {
  color: #ffffff;
}

.theme-toggle button {
  background: #ffffff;
  border-color: #333333;
  color: #333333;
}

body.dark-mode .theme-toggle button {
  background: #1a1a1a;
  border-color: #f0f0f0;
  color: #f0f0f0;
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
  // Create toggle button
  const toggleContainer = document.createElement('div');
  toggleContainer.className = 'theme-toggle';
  
  const toggleButton = document.createElement('button');
  toggleButton.innerHTML = '🌙'; // Moon for dark mode
  toggleButton.title = 'Toggle Dark Mode';
  
  toggleContainer.appendChild(toggleButton);
  document.body.appendChild(toggleContainer);
  
  // Check for saved theme preference
  const savedTheme = localStorage.getItem('theme');
  if (savedTheme === 'dark') {
    document.body.classList.add('dark-mode');
    toggleButton.innerHTML = '☀️'; // Sun for light mode
  }
  
  // Toggle theme on click
  toggleButton.addEventListener('click', function() {
    document.body.classList.toggle('dark-mode');
    const isDark = document.body.classList.contains('dark-mode');
    
    if (isDark) {
      toggleButton.innerHTML = '☀️';
      localStorage.setItem('theme', 'dark');
    } else {
      toggleButton.innerHTML = '🌙';
      localStorage.setItem('theme', 'light');
    }
  });
});
</script>

# Blog

Technical articles about robotics, navigation algorithms and robotics software.

Planned articles:

- Pure Pursuit Explained
- Vector Pursuit vs Pure Pursuit
- Designing PLC Interfaces for AGVs
- Building a High Performance C++ Robotics Stack
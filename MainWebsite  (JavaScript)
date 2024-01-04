//FILE NAME:function.js
function updateDateTime() {
	// Create a new Date object
	var now = new Date();
  
	// Get the current date and time components
	var date = now.toLocaleDateString();
	var time = now.toLocaleTimeString();
  
	// Update the content of the span with the formatted date and time
	document.getElementById('datetime').innerHTML = date + ' ' + time;
  }
  
  // Update the date and time every second (1000 milliseconds)
  setInterval(updateDateTime, 1000);
  
  // Initial update
  updateDateTime();
  const employees = [
	{ name: "John Doe", registrationNumber: "12345", birthday: "2023-04-12" },
	{ name: "Jane Smith", registrationNumber: "67890", birthday: "2023-04-12" },
	// Add more employee data as needed
  ];

  // Function to filter employees with birthdays today
  function getTodaysBirthdays() {
	const today = new Date().toLocaleDateString();

	return employees.filter(employee => {
	  const employeeBirthday = new Date(employee.birthday).toLocaleDateString();
	  return employeeBirthday === today;
	});
  }

  // Function to display birthdays in the container
  function displayBirthdays() {
	const birthdayContainer = document.getElementById("birthdayContainer");
	const todayBirthdays = getTodaysBirthdays();

	if (todayBirthdays.length === 0) {
	  birthdayContainer.innerHTML = "<p>No birthdays today.</p>";
	  return;
	}

	const birthdayList = todayBirthdays.map(employee => {
	  return `<p>${employee.name} (Reg. No: ${employee.registrationNumber})</p>`;
	});

	birthdayContainer.innerHTML = birthdayList.join("");
  }

  // Call the displayBirthdays function when the page loads
  window.onload = displayBirthdays;

  async function fetchCrudeOilValue() {
	try {
	  const response = await fetch('http://localhost:3000/api/crude-oil-value');
	  const data = await response.json();
	  document.getElementById('crudeOilLink').textContent = `Crude Oil: Brent: ${data.value}`;
	} catch (error) {
	  console.error(error);
	}
  }

  // Fetch initial value
  fetchCrudeOilValue();

  // Set up auto-refresh every 5 minutes (adjust as needed)
  setInterval(fetchCrudeOilValue, 5 * 60 * 1000);
  

  

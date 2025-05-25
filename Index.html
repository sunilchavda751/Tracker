<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Compact Year Tracker</title>
  <style>
    body {
      margin: 0;
      background: black;
      font-family: Arial, sans-serif;
      color: white;
      text-align: center;
      font-size: 12px;
    }

    h1 {
      background: #22d3ee;
      color: black;
      display: inline-block;
      padding: 6px 14px;
      border-radius: 6px;
      margin: 10px auto 4px;
      font-size: 14px;
    }

    .bar {
      margin: 6px 0 2px;
    }

    .bar-label {
      font-size: 12px;
      margin-bottom: 2px;
      color: #ccc;
    }

    .bar-boxes {
      display: flex;
      justify-content: center;
      gap: 2px;
      flex-wrap: wrap;
      margin-bottom: 30px;
    }

    .box {
      width: 14px;
      height: 14px;
      background-color: #1e1e1e;
      border: 1px solid #333;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #aaa;
      font-size: 9px;
    }

    .box.active {
      background-color: #22d3ee;
      color: black;
      font-weight: bold;
    }

    .calendar {
      display: grid;
      grid-template-columns: repeat(6, 1fr);
      gap: 5px;
      margin-top: 50px;
      padding: 0 6px;
    }

    .month {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 10px;
    }

    .month-number {
      color: #ccc;
      font-size: 10px;
    }

    .days {
      display: grid;
      grid-template-columns: repeat(6, auto);
      gap: 1px;
    }

    .day {
      width: 7px;
      height: 7px;
      background-color: #1e1e1e;
    }

    .day.active {
      background-color: #22d3ee;
    }
  </style>
</head>
<body>

  <h1 id="currentDate">Loading...</h1>

  <!-- Updated header labels with brackets -->
  <div class="bar">
    <div class="bar-label" id="monthLabel"></div>
    <div class="bar-boxes" id="monthBar"></div>
  </div>

  <div class="bar">
    <div class="bar-label" id="weekLabel"></div>
    <div class="bar-boxes" id="weekBar"></div>
  </div>

  <div class="bar">
    <div class="bar-label" id="dayLabel"></div>
  </div>

  <!-- Month blocks below -->
  <div class="calendar" id="calendarGrid"></div>

  <script>
    const now = new Date();
    const year = now.getFullYear();
    const currentMonth = now.getMonth() + 1;
    const currentDate = now.getDate();
    const start = new Date(year, 0, 0);
    const dayOfYear = Math.floor((now - start) / (1000 * 60 * 60 * 24));
    const currentWeek = Math.ceil((dayOfYear + start.getDay() + 1) / 7);

    document.getElementById("currentDate").innerText = `${currentDate}/${currentMonth}/${year}`;

    // CHANGED: Header format to [ Month - 7 left ]
    document.getElementById("monthLabel").innerText = `[ Month - ${12 - currentMonth} left ]`;
    document.getElementById("weekLabel").innerText = `[ Week - ${52 - currentWeek} left ]`;
    document.getElementById("dayLabel").innerText = `[ Day - ${365 - dayOfYear} left ]`;

    // CHANGED: Compact Month and Week Bars
    function createBar(containerId, total, active) {
      const container = document.getElementById(containerId);
      for (let i = 1; i <= total; i++) {
        const box = document.createElement("div");
        box.className = "box";
        box.innerText = i;
        if (i === active) box.classList.add("active");
        container.appendChild(box);
      }
    }

    // CHANGED: Calendar Layout — 12 compact month blocks
    function createCalendar() {
      const grid = document.getElementById("calendarGrid");
      const monthDays = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31];
      let dayCounter = 1;

      for (let m = 0; m < 12; m++) {
        const monthDiv = document.createElement("div");
        monthDiv.className = "month";

        const label = document.createElement("div");
        label.className = "month-number";
        label.innerText = m + 1;
        monthDiv.appendChild(label);

        const daysWrap = document.createElement("div");
        daysWrap.className = "days";

        for (let d = 1; d <= monthDays[m]; d++) {
          const dBox = document.createElement("div");
          dBox.className = "day";
          if (dayCounter === dayOfYear) dBox.classList.add("active");
          daysWrap.appendChild(dBox);
          dayCounter++;
        }

        monthDiv.appendChild(daysWrap);
        grid.appendChild(monthDiv);
      }
    }

    createBar("monthBar", 12, currentMonth);
    createBar("weekBar", 52, currentWeek);
    createCalendar();
  </script>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
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
      margin-bottom: 10px;
      max-width: 95vw;
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
      grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
      gap: 10px;
      padding: 10px;
      margin: 10px 5px;
    }

    .month {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 6px;
    }

    .month-number {
      color: #ccc;
      font-size: 10px;
    }

    .days {
      display: grid;
      grid-template-columns: repeat(5, 1fr);
      gap: 2px;
    }

    .day {
      width: 10px;
      height: 10px;
      background-color: #222;
    }

    @media (max-width: 500px) {
      .box {
        width: 12px;
        height: 12px;
        font-size: 8px;
      }

      .calendar {
        grid-template-columns: repeat(3, 1fr);
        gap: 8px;
      }

      .days {
        grid-template-columns: repeat(5, 1fr);
        gap: 2px;
      }
    }
  </style>
</head>
<body>
  <h1 id="date">Loading...</h1>

  <div class="bar">
    <div class="bar-label" id="monthLabel">[Month - 7 left]</div>
    <div class="bar-boxes" id="monthBar"></div>
  </div>

  <div class="bar">
    <div class="bar-label" id="weekLabel">[Week - 30 left]</div>
    <div class="bar-boxes" id="weekBar"></div>
  </div>

  <div class="bar">
    <div class="bar-label" id="dayLabel">[Day - 218 left]</div>
    <div class="calendar" id="calendar"></div>
  </div>

  <script>
    const today = new Date();
    const year = today.getFullYear();
    const month = today.getMonth() + 1;
    const week = Math.ceil((getDayOfYear(today) + new Date(year, 0, 1).getDay()) / 7);
    const day = getDayOfYear(today);

    document.getElementById("date").innerText = `${today.getDate()}/${month}/${year}`;
    document.getElementById("monthLabel").innerText = `[Month - ${12 - month} left]`;
    document.getElementById("weekLabel").innerText = `[Week - ${52 - week} left]`;
    document.getElementById("dayLabel").innerText = `[Day - ${365 - day} left]`;

    function getDayOfYear(date) {
      const start = new Date(date.getFullYear(), 0, 0);
      const diff = date - start;
      return Math.floor(diff / (1000 * 60 * 60 * 24));
    }

    function createBar(id, total, active) {
      const bar = document.getElementById(id);
      for (let i = 1; i <= total; i++) {
        const box = document.createElement("div");
        box.className = "box";
        box.textContent = i;
        if (i === active) box.classList.add("active");
        bar.appendChild(box);
      }
    }

    function createCalendar(currentDay) {
      const calendar = document.getElementById("calendar");
      let dayCount = 1;
      for (let m = 1; m <= 12; m++) {
        const month = document.createElement("div");
        month.className = "month";

        const monthNumber = document.createElement("div");
        monthNumber.className = "month-number";
        monthNumber.textContent = m;
        month.appendChild(monthNumber);

        const days = document.createElement("div");
        days.className = "days";

        for (let d = 1; d <= 30; d++) {
          const dayBox = document.createElement("div");
          dayBox.className = "day";
          if (dayCount === currentDay) {
            dayBox.style.backgroundColor = "#22d3ee";
          }
          dayCount++;
          days.appendChild(dayBox);
        }

        month.appendChild(days);
        calendar.appendChild(month);
      }
    }

    createBar("monthBar", 12, month);
    createBar("weekBar", 52, week);
    createCalendar(day);
  </script>
</body>
</html>
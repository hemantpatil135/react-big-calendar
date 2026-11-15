# React Big Calendar with Bar Graph

A machine-coding exercise: plot date-wise data on a calendar and open a bar chart for a day when you select it.

## Features

- **Calendar views:** month, week, day and agenda, via `react-big-calendar` with a Moment localizer.
- **Highlighted data days:** every date in `src/data.json` appears as a calendar event.
- **Drill-down chart:** selecting a day opens a Material UI dialog with a Chart.js bar chart of that day's values, one bar per user.

## Tech stack

React 18 · Vite · react-big-calendar · Chart.js + react-chartjs-2 · Material UI · Moment

## Getting started

```bash
git clone https://github.com/hemantpatil135/react-big-calendar.git
cd react-big-calendar
npm install
npm run dev        # http://localhost:5173
```

The sample data covers **1–5 February 2025**. The calendar opens on today's date, so go back to February 2025 to see the highlighted days.

No environment variables are needed.

## Data format

`src/data.json` maps `DD-MM-YYYY` dates to a list of `{ user: value }` entries:

```json
{
  "01-02-2025": [{ "user_1": 1 }, { "user_2": 2 }, { "user_3": 3 }, { "user_4": 4 }]
}
```

## Project structure

```
src/
├── components/Calender.jsx   # calendar, event mapping, chart dialog
├── data.json                 # sample data
├── App.jsx
└── main.jsx
```

## Known gaps

- Selecting a day **without** data opens an empty chart. The brief asked for a "No data found for the selected date" message instead.
- Clicking an event itself does nothing (`onSelectEvent` isn't wired up). Selection happens through the day slot.

## Possible improvements

- Show a "No data found" message for empty days and wire up `onSelectEvent`
- Replace Moment with `date-fns` or `dayjs` to shrink the bundle
- Add a test for the date-to-chart mapping

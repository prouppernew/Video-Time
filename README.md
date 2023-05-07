# Video-Time
import React, { useState } from "react";
import "../styles/App.css";

const App = () => {
  const [hrs, setHrs] = useState(0);
  const [min, setMin] = useState(0);
  const [speed, setSpeed] = useState(1);
  const [time, setTime] = useState({ hours: 0, minutes: 0 });

  const onButtonClick = () => {
    const totalMins = parseInt(hrs) * 60 + parseInt(min);
    const watchedMins = totalMins / parseFloat(speed);
    const hours = Math.floor(watchedMins / 60);
    const minutes = Math.round(watchedMins % 60);
    setTime({ hours, minutes });
  };

  return (
    <div id="main">
      Put the length of the video
      <br />
      <input
        id="input-hrs"
        value={hrs}
        onChange={(e) => setHrs(e.target.value)}
      />
      hrs
      <input
        id="input-mins"
        value={min}
        onChange={(e) => setMin(e.target.value)}
      />
      min
      <br />
      <br />
      Enter the speed you will watch the video
      <br />
      <input
        id="speed"
        value={speed}
        onChange={(e) => setSpeed(e.target.value)}
      />
      <button id="button" onClick={onButtonClick}>
        Click
      </button>
      <br />
      <br />
      Time to finish the video
      <p id="answer">
        {time.hours}hrs {time.minutes}mins
      </p>
    </div>
  );
};

export default App;

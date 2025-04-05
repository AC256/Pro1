import React, { useState } from "react";
import ReactDOM from "react-dom/client";

function App() {
  const [mood, setMood] = useState("happy");

  const moodVideos = {
    happy: [
      {
        id: 1,
        title: "Try Not To Laugh Challenge 😂",
        url: "https://www.youtube.com/embed/9HBLiJjI7a8",
      },
      {
        id: 2,
        title: "Stand-up Comedy by Zakir Khan",
        url: "https://www.youtube.com/embed/tDgCz2x3CMc",
      },
    ],
    sad: [
      {
        id: 3,
        title: "Funny Cat Compilation",
        url: "https://www.youtube.com/embed/J---aiyznGQ",
      },
      {
        id: 4,
        title: "Wholesome TikToks to Cheer You Up",
        url: "https://www.youtube.com/embed/6d_P5f_C7g4",
      },
    ],
    bored: [
      {
        id: 5,
        title: "Epic Fails Compilation",
        url: "https://www.youtube.com/embed/EtvHhvViDoE",
      },
      {
        id: 6,
        title: "Impossible Try Not To Laugh",
        url: "https://www.youtube.com/embed/9I3tsh54MiY",
      },
    ],
    chill: [
      {
        id: 7,
        title: "Lo-Fi Chill Mix",
        url: "https://www.youtube.com/embed/jfKfPfyJRdk",
      },
      {
        id: 8,
        title: "Relaxing Nature Sounds",
        url: "https://www.youtube.com/embed/1ZYbU82GVz4",
      },
    ],
  };

  return (
    <div className="p-6">
      <h1 className="text-2xl font-bold mb-4">Moodflix 🎭</h1>
      <label className="block mb-2 font-semibold">Select your mood:</label>
      <select
        value={mood}
        onChange={(e) => setMood(e.target.value)}
        className="p-2 border rounded mb-4"
      >
        <option value="happy">😊 Happy</option>
        <option value="sad">😢 Sad</option>
        <option value="bored">😐 Bored</option>
        <option value="chill">😌 Chill</option>
      </select>

      <div className="grid gap-6 grid-cols-1 md:grid-cols-2">
        {moodVideos[mood].map((video) => (
          <div key={video.id} className="rounded overflow-hidden shadow-lg">
            <iframe
              width="100%"
              height="250"
              src={video.url}
              title={video.title}
              frameBorder="0"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
              allowFullScreen
            ></iframe>
            <div className="px-4 py-2">
              <h2 className="font-semibold text-lg">{video.title}</h2>
            </div>
          </div>
        ))}
      </div>
    </div>
  );
}

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

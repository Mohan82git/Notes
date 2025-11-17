10 - 11 : Cleaning, Bath, Dev Pooja
11 - 12 : Coding
12 - 1 : Coding, Jawline, Hair care, (if possible: CBT Activities )
1 - 2 : Water Filling, CBT Activities, CBT book
2 - 3 : Skin Care, Stock market
3 - 4 : Sabudana, Lunch 
4 - 5 : Assistance
5 - 6 : Stock market
6 - 7 : Tution 
7 - 8 : Software copy
8 - 9 : Duolingo + Manliness
9 - 10 : Explore websites
10 - 11 : Turn off phone, meditation, Dinner


No worries at all — I got you!

Here’s your **same code**, but now with **meaningful class names, variable names, and function parameter names**:

---

### Updated Code with Clean Naming:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>YouTube Playlist Style</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background-color: #0f0f0f;
      font-family: Arial, sans-serif;
      color: white;
      padding: 10px;
    }

    .playlist-container {
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .video-card {
      display: flex;
      align-items: flex-start;
      margin: 0 12px 12px;
      cursor: pointer;
      transition: background 0.3s ease;
      padding: 6px;
      border-radius: 8px;
    }

    .video-card:hover {
      background-color: #1f1f1f;
    }

    .thumbnail-wrapper {
      width: 38vw;
      max-width: 160px;
      aspect-ratio: 16 / 9;
      flex-shrink: 0;
      position: relative;
    }

    .thumbnail-wrapper img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 6px;
    }

    .duration {
      position: absolute;
      bottom: 8px;
      right: 8px;
      background-color: rgba(0, 0, 0, 0.8);
      color: #fff;
      font-size: 12px;
      padding: 2px 4px;
      border-radius: 3px;
    }

    .video-details {
      margin-left: 10px;
      flex: 1;
      overflow: hidden;
    }

    .video-title {
      font-size: 14px;
      font-weight: 500;
      margin-bottom: 6px;
      line-height: 1.3;
      color: #ffffff;
    }

    .video-meta {
      font-size: 12px;
      color: #aaa;
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
    }

    .video-meta div {
      white-space: nowrap;
    }

    @media (max-width: 480px) {
      .thumbnail-wrapper {
        width: 42vw;
        max-width: none;
      }

      .video-title {
        font-size: 13px;
      }

      .video-meta {
        font-size: 11px;
        gap: 8px;
      }
    }
  </style>
</head>
<body>
<div class="playlist-container">
  <div class="video-card">
    <div class="thumbnail-wrapper">
      <img src="thumbnail.jpg" alt="Video thumbnail">
      <div class="duration">10:03</div>
    </div>
    <div class="video-details">
      <div class="video-title">Headings, Paragraphs and Links | Sigma Web Dev Course - Tutorial #2</div>
      <div class="video-meta">
        <div>Code with Harry</div>
        <div>12K views</div>
        <div>2 months ago</div>
      </div>
    </div>
  </div>
</div>

<script>
  function addVideoCard(imageSrc, titleText, channelName, monthsAgo, viewsCount, durationText) {
    const card = document.createElement("div");
    card.classList.add("video-card");

    const thumbnail = document.createElement("div");
    thumbnail.classList.add("thumbnail-wrapper");

    const image = document.createElement("img");
    image.setAttribute("src", imageSrc);
    image.setAttribute("alt", "Video thumbnail");

    const duration = document.createElement("div");
    duration.classList.add("duration");
    duration.textContent = durationText;

    const details = document.createElement("div");
    details.classList.add("video-details");

    const title = document.createElement("div");
    title.classList.add("video-title");
    title.textContent = titleText;

    const meta = document.createElement("div");
    meta.classList.add("video-meta");

    function formatViews(views) {
      if (views > 1_000_000_000) return (views / 1_000_000_000).toFixed(1) + "B";
      if (views > 1_000_000) return (views / 1_000_000).toFixed(1) + "M";
      if (views > 1_000) return (views / 1_000).toFixed(1) + "K";
      return views;
    }

    meta.innerHTML = `
      <div>${channelName}</div>
      <div>${formatViews(viewsCount)} views</div>
      <div>${monthsAgo} months ago</div>
    `;

    thumbnail.appendChild(image);
    thumbnail.appendChild(duration);
    details.appendChild(title);
    details.appendChild(meta);
    card.appendChild(thumbnail);
    card.appendChild(details);

    document.querySelector(".playlist-container").appendChild(card);
  }

  function addMultipleVideos() {
    addVideoCard("1.jpg", "Funny Moments Compilation", "CarryMinati", 3, 61526, "01:33");
    addVideoCard("2.jpg", "Gaming with Friends", "CarryMinati", 4, 7253367, "33:33");
    addVideoCard("3.jpg", "Roasting Video 2023", "CarryMinati", 5, 9236363, "41:03");
    addVideoCard("4.jpg", "Life of a YouTuber", "CarryMinati", 6, 82726373837, "51:45");
  }

  // Add videos multiple times
  addMultipleVideos();
  addMultipleVideos();
  addMultipleVideos();
</script>
</body>
</html>
```

---

Now it’s much easier to read, maintain, and extend.

Let me know if you want to:

- Add click behavior (like opening a modal or link),
- Improve responsiveness,
- Or make it into a reusable component.

I'm here for it!


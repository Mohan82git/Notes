# ITS A GAME OF PATIENCE 

- Responsiveness
- Upload trigger
- Upload animation
- add more icons
- Add default file icon as source image
```
<picture>
  <source srcset="actual-image.jpg" type="image/jpeg">
  <img src="default-image.jpg" alt="Image">
</picture>
```

### 
                <div class="file">
                    <img src="./icons/{ext}.svg" onerror="this.onerror=null;this.src='./icons/file.svg';" alt="ICON">
                    <div class="details">
                        <p class="name">{file}</p>
                        <p class="size">{size_str}</p>
                    </div>
                    <img class="download" onclick="window.location='./{X_FOLDER_NAME}/{file}'" src="download.svg"
                        alt="">
                </div>



Animation 

change width and height 
# Images

## Files here

- `team/team-group.jpg` — the team photo used in the hero (1800 × 1200, 228 KB).
- `team/team-group-900.jpg` — the same photo at 900 px, served to phones via `srcset`.
- `logo.svg` — placeholder team mark (three swept blades) used in the header and footer.
  Replace it with your own logo, keeping the filename, and both places update.
- `favicon.svg` — the icon in the browser tab. Replace with your own.

The car and race track on the page are inline SVG diagrams drawn directly in `index.html`,
not image files.

## Adding more photos

Create a folder per area as you need it — `gallery/`, `car/` — and then:

1. **Resize first.** 1600–1800 px on the long edge is plenty. Aim for under 300 KB per file.
   The original team photo was 5184 × 3456 and 6.2 MB; resizing took it to 228 KB with no
   visible loss at the size it is displayed.
2. **Name plainly.** `race-day-launch.jpg`, not `IMG_4821.jpg`.
3. **Use `.jpg` for photos**, `.png` or `.svg` for logos and anything with transparency.
4. **Write a real `alt` description** — say what is happening in the photo. Judges score
   accessibility, and it is the one thing that cannot be done for you.

### Resizing with Python

```powershell
python -c "from PIL import Image, ImageOps; im=ImageOps.exif_transpose(Image.open('in.jpg')).convert('RGB'); im.resize((1800, round(im.height*1800/im.width))).save('out.jpg', quality=82, optimize=True)"
```

See `../NEXT-STEPS.md` for which sections new photos would go into.

# Content Lists with Bootstrap

**DNN Show & Tell, December 1, 2026** · Steve Karpik

At the November 2026 Show & Tell, Jeremy Farrance explained slots in the 2sxc Content App and showed a layout that alternates text and media left and right, styled with Tailwind. This demo rebuilds that layout in Bootstrap 5, three ways, on the same items in one Content App module:

1. **Built-in:** the Content App's own *Image | text* view (nothing to install).
2. **Razor:** `views/Demo Alternating Razor.cshtml` adds `order-lg-last` to every second row. Two switches give alternating, all-left or all-right layouts.
3. **CSS:** `views/Demo Alternating CSS.cshtml` outputs identical rows, and `content-list.css` swaps every even row.

The companion PDF, [Content_Lists_with_Bootstrap.pdf](Content_Lists_with_Bootstrap.pdf), walks through every step.

## Tested with

| Part | Version |
| --- | --- |
| DNN Platform | 10.4.1 |
| 2sxc | 21.7.0 LTS, Content App |
| Theme | 2shine BS5 CA 5.5.0 (Bootstrap 5.3.9) |

Any Bootstrap 5 theme should work. `vstack` and `gap-5` need Bootstrap 5.1 or later.

## Install

1. **Page stylesheet** (only for the CSS view): copy `content-list.css` to the website root. In **Page Settings → Advanced → Appearance**, set **Page Stylesheet** to `/content-list.css`.
2. **View files:** in the Content App, open the code editor (the `<>` toolbar button) and create two *Razor Typed* files in the `bs5` folder. Paste in the contents of the two files in `views/`.
3. **Register the views:** in the Content App admin, go to **Views → +** and add one view per file:
   - Template file: the new `.cshtml`
   - Data model: **List of Content Items**
   - Content type: **TextImage** (shown to editors as *Basic content*)
   - Enable list: on
4. **Use them:** on a Content App module with a few Basic content items, use **Change view** to switch between *Image | text* and the two demo views.

## Notes

- Fields used: `Title`, `Text`, `Image`. Adjust the field names if your content type differs.
- On 2sxc 21 typed items, use `item.String("Title")`. `item.Str(...)` doesn't compile.
- `text-muted` still works in Bootstrap 5.3. Swap in `text-body-secondary` if you want the current class.

## Links

- Jeremy's demo: [The 2sxc Content App – A Visual Explanation of Slots](https://youtu.be/Ki1NEdr_VI0)
- Write-up: [stevekarpik.com/The-Lab](https://stevekarpik.com/The-Lab)
- Videos: [DNN Show & Tell on YouTube](https://www.youtube.com/@DnnShowTell)

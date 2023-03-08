# Parallax Site

Interesting scrolling with parallax effect

## Highlights

- **Сalculation scroll y position**
```javascript
window.addEventListener("scroll", (e) => {
  document.body.style.cssText += `--scrollTop: ${this.scrollY}px`;
});
```

- **Adding scroll braking**

```css
transform: translate3d(0, calc(var(--scrollTop) / 1.6), 0);
```
- **Connecting gsap plugins**

```javascript
ScrollSmoother.create({
  wrapper: ".wrapper",
  content: ".content",
});
```

- **Selecting a similar `transition` for paralax**

```css
transition: var(--transition);
```

## Screenshot

![ezgif com-video-to-gif](https://user-images.githubusercontent.com/113831614/223782594-718d7957-cddc-48ba-b5b2-7cce9d6b1057.gif)

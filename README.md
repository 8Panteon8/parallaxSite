# [Parallax Site](https://8panteon8.github.io/parallaxSite/)

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

# Use with React 
```jsx
const main = useRef();
const [scroll, setScroll] = useState(0);

const handleScroll = () => {
  setScroll(window.scrollY);
};

useEffect(() => {
  window.addEventListener("scroll", handleScroll);
  return () => window.removeEventListener("scroll", handleScroll);
}, []);

useLayoutEffect(() => {
  console.log(scroll);
  const ctx = gsap.context(() => {
    ScrollSmoother.create({
      effects: true,
    });
  }, main);
  return () => ctx.revert();
}, []);


return (
  <div id="smooth-wrapper" ref={main}>
    <div id="smooth-content" style={{ "--scrollTop": scroll + "px" }}>
      <You components/>
    </div>
  </div>
);

```



## Screenshot

![ezgif com-video-to-gif](https://user-images.githubusercontent.com/113831614/223782594-718d7957-cddc-48ba-b5b2-7cce9d6b1057.gif)

# grid-layout

## Demo in codepen

[grid-layout](https://codepen.io/yvonne11yuting/pen/YOpVXm?editors=1100)

## Main Idea

### html
container(div.body)內先設置各個區塊（header, main, nav, footer)

```html
<div class="body">
  <header>Header</header>
  <main>Main</main>
  <nav>Navigation</nav>
  <footer>Footer</footer>
</div>
```

設置完html後，在外層的container加上grid相關設定
1. **display: grid;** //使用gird排版<br>
  display: grid | inline-grid;
2. **grid-template-columns** //每一列的寬度分配<br>
  fr(片段,fraction)<br>
  container每個subconatiner所佔的比例<br>
  如：1:1:1 即 1fr 1fr 1fr 即 repear(3, 1fr) 即<br>
  會有三個等比例的subcontainer出現在同一列
3. **grid-auto-rows** //每一行所有subcontainer的高度<br>
  在這邊和grid-template-rows最大的差異是牽一髮而動全身(?!)<br>
  我只需要設定一個數值就可以設定每個subconatiner的default高度<br>
  **minmax(30px, auto)**可以設定最小＆最大值
4. **grid-gap** //  每塊subcontainer和subcontainer之間的間距
5. **grid-template-areas** //版型排法，需搭配grid-area服用<br>
  每個string都是一列，在其中設定grid-area的名字設定所佔比例<br>
  有三個string代表有三行
6. **grid-area** //在subconatiner內設定名字

可搭配media query輕易實現RWD

```css
.body {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* repeat(3, 1fr) = 1fr 1fr 1fr */
  grid-auto-rows: minmax(30px, auto);
  grid-gap: 10px;
  grid-template-areas:
    "header header header"
    "nav main main"
    "footer footer footer";
}

header {
  grid-area: header;
}

main {
  grid-area: main;
}

nav {
  grid-area: nav;
}

footer {
  grid-area: footer;
}
```

## References
1. [CSS Grid Explained in 7 Minutes (with diagrams and code)](https://www.youtube.com/watch?v=ojKbYz0iKQE)
2. [Basic concepts of grid layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout)


## Nested Div (Style)

```
h1 {
    text-align: center;
}

.container {
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
}

.service {
    width: 300px;
    text-align: center;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 10px;
    box-shadow: 0 2px 8px #ccc;
}

.service img {
    max-width: 100%;
    height: 200px;
    object-fit: contain;
}

.service button {
    padding: 8px 12px;
    margin: 5px;
    cursor: pointer;
}

```

## Web Structure (Non-Semantic)

### 1. HTML

```
<!-- Header -->
    <div id="header">
        <h1>ชื่อเว็บไซต์</h1>
        <div id="nav">
            <a href="#" class="nav-item">หน้าแรก</a>
            <a href="#" class="nav-item">สมัครสมาชิก</a>
            <a href="#" class="nav-item">ติดต่อเรา</a>
        </div>
    </div>
    
    <div id="main">
        <!-- Content -->
        <div id="content">
            <div class="article">
                <h2>บทความเกี่ยวกับน้องหมา</h2>
                <div class="detail">
                    <img src="images/dog.jpg" width="200">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cumque perspiciatis itaque culpa dicta
                        beatae, voluptatem quasi in repellendus quidem nostrum quisquam eligendi,</p>
                </div>
            </div>
            <div class="article">
                <h2>บทความเกี่ยวกับน้องแมว</h2>
                <div class="detail">
                    <img src="images/cat.jpg" width="200">
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cumque perspiciatis itaque culpa dicta
                        beatae, voluptatem quasi in repellendus quidem nostrum quisquam eligendi,</p>
                </div>
            </div>
            <!-- Pagination -->
            <div class="pagination">
                <a href="#" class="page-btn active">1</a>
                <a href="#" class="page-btn">2</a>
                <a href="#" class="page-btn">3</a>
                <a href="#" class="page-btn">...</a>
                <a href="#" class="page-btn">Last</a>
            </div>
        </div>
         <!-- Sidebar -->
        <div id="sidebar">
            <div class="widget">
                <h3 class="widget-title">โฆษณา</h3>
                <div class="widget-item">
                    <img src="images/banner.png" height="520" alt="แบนเนอร์โฆษณา">
                </div>
            </div>
        </div>
    </div>
    <!-- Footer -->
    <div id="footer">© 3026 KongRuksiam </div>

```


### 2. Style

```
*,
*::before,
*::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Sarabun', sans-serif;
    background: rgb(255, 255, 255);
    color: #1a1a1c;
    min-height: 100vh;
}

/* ── HEADER ── */
#header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 2rem;
    height: 56px;
    background: #1a1a1c;
    position: sticky;
    top: 0;
    z-index: 100;
}

h1{
    font-family: 'IBM Plex Mono', monospace;
    font-weight: 600;
    font-size: 1.1rem;
    color: #ffffff;
    letter-spacing: -.02em;
}

#nav {
    display: flex;
    gap: .25rem;
}

.nav-item {
    padding: .4rem .9rem;
    font-size: .85rem;
    color: #a0a09a;
    border-radius: 6px;
    cursor: pointer;
    text-decoration: none;
}

.nav-item:hover {
    background: #2e2e32;
    color: #ffffff;
}

/* ── MAIN LAYOUT ── */
#main {
    display: flex;
    gap: 1.5rem;
    max-width: 900px;
    margin: 2rem auto;
    padding: 0 1.5rem;
    align-items: flex-start;
}

/* ── CONTENT ── */
#content {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 1.25rem;
}

.article {
    background: #ffffff;
    border: 1px solid #e4e2dc;
    border-radius: 12px;
    padding: 1.5rem 1.75rem;
    transition: box-shadow .2s;
}

.article:hover {
    box-shadow: 0 4px 20px rgba(0, 0, 0, .07);
}

.article h2 {
    font-size: 1rem;
    font-weight: 700;
    color: #1a1a1c;
    margin-bottom: .6rem;
    padding-bottom: .6rem;
    border-bottom: 2px solid #f0ede6;
}

.detail{
    font-size: .88rem;
    color: #6b6b66;
    line-height: 1.7;
}

.detail img {
    display: block;
    margin: 0 auto 1rem;
}

/* ── SIDEBAR ── */
#sidebar {
    width: 210px;
    flex-shrink: 0;
    position: sticky;
    top: 72px;
}

.widget {
    background: #ffffff;
    border: 1px solid #e4e2dc;
    border-radius: 12px;
    padding: 1.1rem 1.25rem;
    font-size: .85rem;
    font-weight: 600;
    color: #1a1a1c;
}

.widget-title {
    font-family: 'IBM Plex Mono', monospace;
    font-size: .65rem;
    font-weight: 400;
    color: #b0ada6;
    text-transform: uppercase;
    letter-spacing: .08em;
    margin-bottom: .75rem;
}

.widget-item {
    display: flex;
    gap: .65rem;
    align-items: flex-start;
    padding: .6rem 0;
    border-bottom: 1px solid #f0ede6;
    cursor: pointer;
}

.widget-item:last-child {
    border-bottom: none;
    padding-bottom: 0;
}

.widget-item img {
    object-fit: cover;
    border-radius: 6px;
    flex-shrink: 0;
    display: block;
    margin: 0 auto 1rem;
}

.widget-item-title {
    font-size: .78rem;
    font-weight: 600;
    color: #1a1a1c;
    line-height: 1.4;
}

/* ── PAGINATION ── */
.pagination {
    display: flex;
    align-items: center;
    gap: .4rem;
    background: #ffffff;
    border: 1px solid #e4e2dc;
    border-radius: 12px;
    padding: 1rem 1.5rem;
}

.page-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 34px;
    height: 34px;
    border-radius: 8px;
    font-size: .85rem;
    font-family: 'IBM Plex Mono', monospace;
    color: #6b6b66;
    cursor: pointer;
    border: 1px solid transparent;
    text-decoration: none;
}

.page-btn:hover {
    background: #f4f2ee;
    border-color: #e4e2dc;
}

.page-btn.active {
    background: #1a1a1c;
    color: #ffffff;
}

/* ── FOOTER ── */
#footer {
    text-align: center;
    padding: 1.5rem;
    font-size: .78rem;
    color: #a0a09a;
    border-top: 1px solid #e4e2dc;
    margin-top: 2rem;
    font-family: 'IBM Plex Mono', monospace;
}

```

## Web Structure (Semantic)

### Style

```
*,
*::before,
*::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Sarabun', sans-serif;
    background: rgb(255, 255, 255);
    color: #1a1a1c;
    min-height: 100vh;
}

/* ── HEADER ── */
header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 2rem;
    height: 56px;
    background: #1a1a1c;
    position: sticky;
    top: 0;
    z-index: 100;
}

h1 {
    font-family: 'IBM Plex Mono', monospace;
    font-weight: 600;
    font-size: 1.1rem;
    color: #ffffff;
    letter-spacing: -.02em;
}

nav {
    display: flex;
    gap: .25rem;
}

.nav-item {
    padding: .4rem .9rem;
    font-size: .85rem;
    color: #a0a09a;
    border-radius: 6px;
    cursor: pointer;
    text-decoration: none;
}

.nav-item:hover {
    background: #2e2e32;
    color: #ffffff;
}

/* ── MAIN LAYOUT ── */
main {
    display: flex;
    gap: 1.5rem;
    max-width: 900px;
    margin: 2rem auto;
    padding: 0 1.5rem;
    align-items: flex-start;
}

/* ── CONTENT ── */
.content {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 1.25rem;
}

article {
    background: #ffffff;
    border: 1px solid #e4e2dc;
    border-radius: 12px;
    padding: 1.5rem 1.75rem;
    transition: box-shadow .2s;
}

article:hover {
    box-shadow: 0 4px 20px rgba(0, 0, 0, .07);
}

article h2 {
    font-size: 1rem;
    font-weight: 700;
    color: #1a1a1c;
    margin-bottom: .6rem;
    padding-bottom: .6rem;
    border-bottom: 2px solid #f0ede6;
}

.detail {
    font-size: .88rem;
    color: #6b6b66;
    line-height: 1.7;
}

.detail img {
    display: block;
    margin: 0 auto 1rem;
}

/* ── SIDEBAR ── */
aside {
    width: 210px;
    flex-shrink: 0;
    position: sticky;
    top: 72px;
}

.widget {
    background: #ffffff;
    border: 1px solid #e4e2dc;
    border-radius: 12px;
    padding: 1.1rem 1.25rem;
    font-size: .85rem;
    font-weight: 600;
    color: #1a1a1c;
}

.widget-title {
    font-family: 'IBM Plex Mono', monospace;
    font-size: .65rem;
    font-weight: 400;
    color: #b0ada6;
    text-transform: uppercase;
    letter-spacing: .08em;
    margin-bottom: .75rem;
}

.widget-item {
    display: flex;
    gap: .65rem;
    align-items: flex-start;
    padding: .6rem 0;
    border-bottom: 1px solid #f0ede6;
    cursor: pointer;
}

.widget-item:last-child {
    border-bottom: none;
    padding-bottom: 0;
}

.widget-item img {
    object-fit: cover;
    border-radius: 6px;
    flex-shrink: 0;
    display: block;
    margin: 0 auto 1rem;
}

/* ── PAGINATION ── */
.pagination {
    display: flex;
    align-items: center;
    gap: .4rem;
    background: #ffffff;
    border: 1px solid #e4e2dc;
    border-radius: 12px;
    padding: 1rem 1.5rem;
}

.page-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 34px;
    height: 34px;
    border-radius: 8px;
    font-size: .85rem;
    font-family: 'IBM Plex Mono', monospace;
    color: #6b6b66;
    cursor: pointer;
    border: 1px solid transparent;
    text-decoration: none;
}

.page-btn:hover {
    background: #f4f2ee;
    border-color: #e4e2dc;
}

.page-btn.active {
    background: #1a1a1c;
    color: #ffffff;
}

/* ── FOOTER ── */
footer {
    text-align: center;
    padding: 1.5rem;
    font-size: .78rem;
    color: #a0a09a;
    border-top: 1px solid #e4e2dc;
    margin-top: 2rem;
    font-family: 'IBM Plex Mono', monospace;
}

```


## Meta

### 1. Description

```
เว็บไซต์ให้ความรู้เกี่ยวกับการดูแลสัตว์เลี้ยง ทั้งสุนัข แมว อาหาร สุขภาพ และเคล็ดลับสำหรับคนรักสัตว์
```

### 2. Keywords

```
สัตว์เลี้ยง, สุนัข, แมว, การดูแลสัตว์เลี้ยง, อาหารสัตว์, สุขภาพสัตว์
```
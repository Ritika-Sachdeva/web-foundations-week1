# Understanding Web Vitals

## 1. Web Vitals vs Core Web Vitals
**Web Vitals** is a set of metrics from Google to measure the quality of user experience on the web.  
**Core Web Vitals** are the most important subset of these metrics that Google uses for ranking and performance evaluation — currently LCP, FID (moving to INP), and CLS.  

**Real-life analogy:**  
Think of Web Vitals as all the health tests you can take, but Core Web Vitals are the three key tests your doctor insists you check every year.

---

## 2. First Contentful Paint (FCP)
Measures the time from when the page starts loading to when any part of the content (text, image, canvas) is first visible on the screen.  
A fast FCP makes users feel that the page is loading quickly.

**Example:**  
If you open a news site and the top headline text appears after 1.2 seconds — that’s the FCP.

---

## 3. Largest Contentful Paint (LCP)
Tracks the time it takes for the largest visible content element (often a hero image, banner, or headline) to appear.  
LCP focuses on loading performance and should ideally be **≤ 2.5 seconds**.

**Example:**  
On an e-commerce site, the big product image loading is your LCP moment.

---

## 4. Total Blocking Time (TBT)
Measures the total time between **First Contentful Paint** and **Time to Interactive** where the main thread was blocked for long tasks (>50ms).  
Lower TBT means the page responds quickly to user input.

**Example:**  
If a heavy JavaScript animation freezes the page for half a second while loading, it increases TBT.

---

## 5. Cumulative Layout Shift (CLS)
Quantifies unexpected visual shifts of content while the page is loading.  
A low CLS (≤ 0.1) ensures elements don’t jump around, avoiding accidental clicks.

**Example:**  
You’re about to tap “Buy Now” but the button shifts down and you hit “Cancel” instead — that’s high CLS.

---

## 6. Speed Index (SI)
Shows how quickly the visible parts of the page are displayed during load.  
It’s calculated by comparing visual completeness over time — lower is better.

**Example:**  
Two sites load fully in 5s, but one shows most of its content in 1s while the other stays blank until 4s — the first has a better SI.

---

## 7. Lab Data vs Field Data
**Lab Data:** Collected in a controlled environment (like Lighthouse in Chrome DevTools). Useful for debugging but may not reflect real user conditions.  
**Field Data:** Collected from real users via tools like Chrome User Experience Report (CrUX). Shows actual performance in the wild.

**Analogy:**  
Lab data is like a car’s fuel efficiency tested in perfect conditions; field data is how it performs in city traffic.

## Ideal Web Vitals Metrics (Based on Google Web Vitals Documentation)

I referred to the official [Web Vitals documentation](https://web.dev/vitals/) by Google to understand the target values for each key performance metric. These thresholds are based on research into user experience, measuring what feels "fast" and smooth for real-world visitors. They are also considered by Google as ranking signals for SEO.

| Metric | Good | Needs Improvement | Poor |
|--------|------|-------------------|------|
| **LCP (Largest Contentful Paint)** | ≤ 2.5 s | 2.5–4.0 s | > 4.0 s |
| **INP (Interaction to Next Paint)** *(replaces FID)* | ≤ 200 ms | 200–500 ms | > 500 ms |
| **CLS (Cumulative Layout Shift)** | ≤ 0.1 | 0.1–0.25 | > 0.25 |
| **TBT (Total Blocking Time)** | ≤ 200 ms | 200–600 ms | > 600 ms |
| **FCP (First Contentful Paint)** | ≤ 1.8 s | 1.8–3.0 s | > 3.0 s |
| **Speed Index** *(not a Core Web Vital)* | ≤ 3.4 s | 3.4–5.8 s | > 5.8 s |

### Why These Thresholds Matter
- **User Experience:** Sites meeting these thresholds feel faster and smoother, leading to higher engagement.
- **SEO Impact:** Google considers Core Web Vitals as a ranking factor, especially for mobile search results.
- **Industry Standard:** These metrics are defined based on Chrome User Experience Report (CrUX) data from real-world usage.
---
## Understanding Lighthouse Scores

### 1. Performance Score
- **What it measures:**  
  How fast and smooth the page loads and becomes usable, based on metrics like **FCP**, **LCP**, **TBT**, **CLS**, and **Speed Index**.
- **Why it matters:**  
  A higher score means better user experience and better chances of ranking higher in search engines.
- **Example:**  
  A news site with fast headline loading, smooth scrolling, and no layout shifts will have a high performance score.

---

### 2. Accessibility Score
- **What it measures:**  
  How well the page can be used by people with disabilities, including screen reader compatibility, color contrast, ARIA labels, and keyboard navigation.
- **Why it matters:**  
  Improves usability for all users and may be required by law in some countries.
- **Example:**  
  Ensuring buttons have descriptive labels so a screen reader can read them out.

---

### 3. Best Practices Score
- **What it measures:**  
  General coding and security health of the site — like avoiding browser errors, using HTTPS, secure JavaScript libraries, proper image formats, and safe cross-origin use.
- **Why it matters:**  
  Reduces security risks, ensures stable performance, and follows web development standards.
- **Example:**  
  Using HTTPS and loading third-party scripts in a safe way.

---

### 4. SEO Score
- **What it measures:**  
  How well the page follows search engine optimization guidelines, including meta tags, mobile-friendliness, crawlability, and correct HTML structure.
- **Why it matters:**  
  Helps search engines understand and rank your site better.
- **Example:**  
  Having proper `<title>` tags, `<meta description>`, and responsive design.

---
## Ideal Thresholds for Lighthouse Categories

1. **Performance**
   - **Goal:** Higher is better.
   - **Ideal Score:** 90–100 (Green zone).
   - **Reason:** Indicates the site loads fast, is responsive, and meets Core Web Vitals thresholds.

2. **Accessibility**
   - **Goal:** Higher is better.
   - **Ideal Score:** 100 or as close as possible.
   - **Reason:** Ensures the site is usable for people with disabilities (screen readers, keyboard navigation, etc.).

3. **Best Practices**
   - **Goal:** Higher is better.
   - **Ideal Score:** 100.
   - **Reason:** Reflects adherence to modern web development standards, security measures, and safe coding practices.

4. **SEO**
   - **Goal:** Higher is better.
   - **Ideal Score:** 100.
   - **Reason:** Improves visibility in search engines and ensures pages meet search indexing best practices.
---

In my testing, I have compared my Lighthouse results for both desktop and mobile versions of the selected websites against these ideal values to determine areas of improvement.

## Practical Investigation

(Comparing two very different types of websites:

High-traffic, content-heavy (BBC) vs lightweight, optimized corporate site (Fleet Studio))

Tested two websites for Core Web Vitals and related metrics using **Lighthouse** in Chrome DevTools.  
The following table summarises the results (Run 2):

| Site              | Device  | FCP   | LCP   | TBT    | CLS   | SI    | Performance Score | Accessibility | Best Practices | SEO |
|-------------------|---------|-------|-------|--------|-------|-------|-------------------|---------------|----------------|-----|
| fleetstudio.com   | Mobile  | 3.7s  | 6.0s  | 140ms  | 0.002 | 5.1s  | 66                | 84            | 75             | 82  |
| fleetstudio.com   | Desktop | 2.4s  | 2.6s  | 0ms    | 0     | 2.7s  | 71                | 84            | 78             | 82  |
| bbc.com           | Mobile  | 4.7s  | 2.9s  | 1650ms | 0     | 7.2s  | 45                | 90            | 75             | 100 |
| bbc.com           | Desktop | 1.1s  | 0.7s  | 130ms  | 0     | 1.4s  | 94                | 96            | 74             | 100 |

---

## Performance Comparison Insight – BBC vs Fleet Studio

### Why BBC (Desktop) Outperforms Fleet Studio Despite Being Content-Heavy

1. **Advanced Performance Engineering at BBC**
   - Uses aggressive caching and global CDN delivery.
   - Preloads critical CSS, fonts, and hero images.
   - Implements lazy loading for non-critical assets.

2. **Fleet Studio’s Bottlenecks**
   - Large hero image delays **Largest Contentful Paint (LCP)**.
   - Render-blocking CSS/JS slows down **First Contentful Paint (FCP)**.
   - Some unused JavaScript still loads unnecessarily.

3. **Impact of Device & Test Conditions**
   - BBC’s desktop tests benefit from high CPU and network speeds in Lighthouse.
   - Fleet’s site has delivery delays even with fewer resources.

4. **Mobile Performance Difference**
   - BBC mobile score drops due to heavy payload (~2.8MB) and high JavaScript execution time (4.3s+).
   - Fleet’s smaller payload gives it an advantage on mobile despite some optimization issues.

5. **Key Lesson**
   - Performance is not only about **content size** — engineering practices like **critical resource prioritization, caching, and code efficiency** can make large sites load faster than small ones.


### Top Issues

**Fleetstudio – Mobile**
1. Large LCP element (hero image) without preload.
2. Speed Index slowed by unoptimized render-critical resources.
3. Minor unused JavaScript increasing load time.

**Fleetstudio – Desktop**
1. Slightly large LCP due to render-blocking assets.
2. Avoidable unused JavaScript (~78KB).
3. Minor image optimization needed.

**BBC – Mobile**
1. Reduce JavaScript execution time – 4.3s.
2. Minimize main-thread work – 8.0s.
3. Reduce unused JavaScript – ~448KB.

**BBC – Desktop**
1. Reduce unused JavaScript – ~532KB.
2. Properly size images – save ~104KB.
3. Avoid enormous network payloads – ~2.94MB.

---

### Root-Cause Notes

- **FCP**
  - BBC mobile has a slower FCP due to heavy JavaScript and large payload.
  - Fleetstudio mobile FCP is delayed by CSS and JS blocking above-the-fold rendering.

- **LCP**
  - Fleetstudio mobile LCP (6.0s) is poor because of a large hero image and late loading.
  - BBC mobile LCP is acceptable but could be improved with preload optimization.

- **TBT**
  - BBC mobile TBT (1650ms) is very high because of third-party scripts and long tasks blocking the main thread.
  - Fleetstudio sites have low TBT due to lighter JavaScript execution.

- **CLS**
  - All tested versions have CLS close to 0, indicating well-reserved element space.

- **SI**
  - BBC mobile has high SI (7.2s) as visible content appears late in the load process.
  - Fleetstudio mobile SI (5.1s) is moderately high due to render-blocking resources.

---

### Recommendations

1. **Reduce LCP**
   - Compress and resize hero images.
   - Serve images in next-gen formats like WebP/AVIF.
   - Add `<link rel="preload">` for above-the-fold images.

2. **Improve TBT**
   - Defer non-critical JavaScript.
   - Split long-running JS tasks into smaller chunks.
   - Load third-party scripts asynchronously.

3. **Lower SI**
   - Streamline render-critical CSS and JS.
   - Reduce the number of blocking requests in the critical path.
   - Inline critical CSS for the first viewport.

4. **Maintain CLS**
   - Continue reserving fixed space for images, ads, and embeds.
   - Use `font-display: swap` to avoid layout shifts due to font loading.

---

### Most Impactful Fix

For **BBC Mobile**, reducing unused JavaScript and limiting third-party script impact would **significantly decrease TBT** and improve the performance score from 45 to potentially above 80.

---
## Why Measuring Web Vitals Matters
- **User Retention:** Faster, smoother websites reduce bounce rates and keep visitors engaged.
- **Business Impact:** Even a 0.1s improvement in load time can increase conversion rates.
- **Search Rankings:** Google uses Core Web Vitals in its ranking algorithm, especially for mobile.
- **Accessibility & Inclusivity:** Optimizing for accessibility ensures a better experience for all users.

---
## Why We Need to Check Web Vitals in Development

### **User Experience is Everything**
Imagine you open Amazon, and it takes **10 seconds** before you can even click anything.  

Users don’t care if your backend is complex or your JavaScript is “beautiful” — if it feels slow, they leave.  

**Web Vitals** measure:
- How quickly users see content
- How soon they can interact
- How stable the page layout looks

---

### **Direct Impact on SEO & Traffic**
- Google officially uses **Core Web Vitals** as a ranking signal.
- A fast, stable site → ranks higher → more visibility → more users.
- If two websites have similar content, the faster one will usually rank better.

---

### **Higher Conversions = More Revenue**
- Amazon found that **every 100ms** of extra load time reduced sales by ~**1%**.
- For an e-commerce platform, that’s **millions lost** just because of performance delays.

---

### **Performance Issues Are Cheaper to Fix Early**
- During development, you can spot bottlenecks (large images, blocking scripts) **before launch**.
- Fixing issues **after going live** is more expensive and can impact real customers.

---

### **Mobile Users Are More Sensitive**
- Over **60%** of internet traffic is from mobile devices.
- Mobile networks are slower, and devices have weaker CPUs.
- **Optimizing for mobile is critical** to avoid losing this majority audience.

---

### **How to Think of It**
It’s like building a shop:
- **FCP** = How quickly people see your shop sign.
- **LCP** = How quickly the main display is ready.
- **TBT / TTI** = How soon they can walk in and ask for something.
- **CLS** = Making sure the door doesn’t suddenly move when they’re entering.

If any of these fail, people will just go to a competitor’s shop.
---
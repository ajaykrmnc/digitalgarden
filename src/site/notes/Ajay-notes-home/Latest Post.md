---
{"dg-publish":true,"permalink":"/ajay-notes-home/latest-post/"}
---



```
const excludedFolders = ["Templates", "Private", "Daily/Journal"];
const pages = dv.pages()
    .filter(p => p["dg-publish"] === true)
    .filter(p => !excludedFolders.some(folder => p.file.path.startsWith(folder + "/")))
    .sort(p => p.file.ctime, 'desc')
    .slice(0, 10);

for (let page of pages) {
    const rawDate = page.file.ctime;
    const suffix = (n) => {
        if (n > 3 && n < 21) return 'th';
        switch (n % 10) {
            case 1: return 'st';
            case 2: return 'nd';
            case 3: return 'rd';
            default: return 'th';
        }
    };
    const day = rawDate.day;
    const dateFormatted = `${day}${suffix(day)} ${rawDate.toFormat("LLLL yyyy")}`;

    const title = page.title ?? page.file.name;
    const tags = (page.tags ?? []).map(tag => `<span class="tag">${tag.toUpperCase()}</span>`).join(" ");
    const desc = page.description ?? "";
    const link = page.file.link;
     const rel_path = page.file.path

    const container = dv.container.createEl("div", { cls: "post-preview" });
    container.innerHTML = `
	     <div class="post-date">${dateFormatted}</div> 
	     <div class="post-title"><a href="${link}">${title}</a></div> 
	     <div class="post-tags">${tags}</div>
	    <div class="post-desc">${desc}</div> 
	     <div class="post-link"><a class = "internal-link"></a>
    ${link} <hr> `;
	// No need to return anything; the container is already created.
}
```

<a data-tooltip-position="top" aria-label="Coding/Productivity/TheEconomist Magazine to Kindle.md" data-href="Coding/Productivity/TheEconomist Magazine to Kindle.md" href="Coding/Productivity/TheEconomist Magazine to Kindle.md" class="internal-link" target="_blank" rel="noopener nofollow">TheEconomist Magazine to Kindle</a>

<a href="Coding/Productivity/TheEconomist Magazine to Kindle.md" class = "internal-link"><span>Read More -&gt;</span></a>

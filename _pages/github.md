---
layout: single
title: "💻 GitHub Repositories"
permalink: /github/
author_profile: true
---

This page collects the public repositories where I share **research software**, **reproducible computational experiments**, **teaching material**, and **supporting code for publications**. The projects span nonlinear dynamics, uncertainty quantification, scientific machine learning, optimization, computational mechanics, and epidemiological modeling.

<a href="https://github.com/americocunhajr" target="_blank" class="btn btn-outline-primary btn-sm">🐙 GitHub Profile</a>
<a href="/software/" class="btn btn-outline-primary btn-sm">🖥️ Software</a>

---

## 📌 Featured Research Software

<div id="github-featured">
  <p>🔄 Loading featured repositories...</p>
</div>

---

## 📦 Public Repositories

The list below is loaded directly from GitHub and ordered by the most recently updated repositories.

<div id="github-repositories">
  <p>🔄 Loading repositories...</p>
</div>

<script>
(function () {
  const username = "americocunhajr";
  const featuredOrder = [
    "mSINDy",
    "DynaMoDE",
    "BistableX",
    "CEopt",
    "STONEHENGE",
    "ARBO"
  ];

  function repoEmoji(repo) {
    const text = `${repo.name} ${repo.description || ""}`.toLowerCase();

    if (/dengue|zika|chikungunya|epid|covid|arbovirus/.test(text)) return "🦠";
    if (/origami|metamaterial/.test(text)) return "🦢";
    if (/harvest|energy/.test(text)) return "🔋";
    if (/uncertainty|\buq\b|random|probab|sobol|maxent/.test(text)) return "🎲";
    if (/optim|ceopt|cross-opt|suspension/.test(text)) return "🎯";
    if (/machine learning|neural|sindy|dmd|koopman|data-driven|ai-|artificial intelligence/.test(text)) return "🤖";
    if (/nonlinear|chaos|dynamic|vibration|mechanic|electrom/.test(text)) return "🌀";
    if (/latex|beamer/.test(text)) return "📝";
    if (/course|uerj|lncc|princeton/.test(text)) return "🎓";
    return "📦";
  }

  function repoRow(repo) {
    const description = repo.description || "Public GitHub repository.";
    const updated = new Intl.DateTimeFormat("en", {
      year: "numeric",
      month: "short",
      day: "2-digit"
    }).format(new Date(repo.updated_at));

    const language = repo.language ? ` · 💻 ${repo.language}` : "";
    const license = repo.license && repo.license.spdx_id
      ? ` · 📜 ${repo.license.spdx_id}`
      : "";
    const homepage = repo.homepage
      ? `<a href="${repo.homepage}" target="_blank" class="btn btn-outline-primary btn-sm">🌐 Website</a>`
      : "";

    return `
      <table style="width:100%; margin-bottom:15px; border-collapse:collapse; border:none; table-layout:fixed; border-spacing:0;">
        <tr>
          <td style="width:72px; text-align:center; vertical-align:middle; border:none; font-size:34px;">
            ${repoEmoji(repo)}
          </td>
          <td style="padding-left:15px; vertical-align:middle; border:none;">
            <h3 style="margin-bottom:5px; font-size:18px; color:#3f51b5;">${repo.name}</h3>
            <span style="font-size:14px; color:#777;">${description}</span><br>
            <span style="font-size:12px; color:#999;">⭐ ${repo.stargazers_count} · 🔀 ${repo.forks_count}${language}${license} · 🕒 ${updated}</span><br>
            <a href="${repo.html_url}" target="_blank" class="btn btn-outline-primary btn-sm">💻 Repository</a>
            ${homepage}
          </td>
        </tr>
      </table>`;
  }

  fetch(`https://api.github.com/users/${username}/repos?per_page=100&sort=updated`)
    .then(response => {
      if (!response.ok) throw new Error("GitHub API request failed");
      return response.json();
    })
    .then(repositories => {
      const repos = repositories.filter(repo => !repo.fork);
      const byName = new Map(repos.map(repo => [repo.name, repo]));
      const featured = featuredOrder
        .map(name => byName.get(name))
        .filter(Boolean);
      const featuredSet = new Set(featured.map(repo => repo.name));
      const remaining = repos.filter(repo => !featuredSet.has(repo.name));

      document.getElementById("github-featured").innerHTML = featured.length
        ? featured.map(repoRow).join("")
        : "<p>⚠️ Featured repositories are temporarily unavailable.</p>";

      document.getElementById("github-repositories").innerHTML = remaining.length
        ? remaining.map(repoRow).join("")
        : "<p>⚠️ Repository data are temporarily unavailable.</p>";
    })
    .catch(() => {
      const fallback = `
        <p>⚠️ GitHub repository data could not be loaded automatically.</p>
        <p><a href="https://github.com/${username}" target="_blank" class="btn btn-outline-primary btn-sm">🐙 Open GitHub Profile</a></p>`;
      document.getElementById("github-featured").innerHTML = fallback;
      document.getElementById("github-repositories").innerHTML = fallback;
    });
})();
</script>

---

### 📌 Notes

- 🛠️ Most repositories are **open-source** and intended for research, education, and reproducible computational science.
- 📚 Project-specific documentation, references, and citation instructions are provided inside the corresponding repositories whenever available.
- 🤝 Contributions, discussions, and collaborations are welcome through the relevant GitHub repository.

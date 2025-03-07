<!--header-->
<table>
  <tr><th colspan="2"><h3>🗂️ Active projects</h3></th></tr>
  <tr><td colspan="2" align="center"><p>This plugin displays progress of your profile and repository projects.</p>
</td></tr>
  <tr>
    <th rowspan="3">Supported features<br><sub><a href="metadata.yml">→ Full specification</a></sub></th>
    <td><a href="/source/templates/classic/README.md"><code>📗 Classic template</code></a> <a href="/source/templates/repository/README.md"><code>📘 Repository template</code></a></td>
  </tr>
  <tr>
    <td><code>👤 Users</code> <code>👥 Organizations</code> <code>📓 Repositories</code></td>
  </tr>
  <tr>
    <td><code>🔑 (scopeless)</code> <code>🔑 public_repo</code> <code>read:org (optional)</code> <code>read:user (optional)</code> <code>repo (optional)</code></td>
  </tr>
  <tr>
    <td colspan="2" align="center">
      <img src="https://github.com/lowlighter/metrics/blob/examples/metrics.plugin.projects.svg" alt=""></img>
      <img width="900" height="1" alt="">
    </td>
  </tr>
</table>
<!--/header-->

## ➡️ Available options

<!--options-->
<table>
  <tr>
    <td align="center" nowrap="nowrap">Type</i></td><td align="center" nowrap="nowrap">Description</td>
  </tr>
  <tr>
    <td nowrap="nowrap"><code>plugin_projects</code></td>
    <td rowspan="2"><p>Enable projects plugin</p>
<img width="900" height="1" alt=""></td>
  </tr>
  <tr>
    <td nowrap="nowrap"><b>type:</b> <code>boolean</code>
<br>
<b>default:</b> no<br></td>
  </tr>
  <tr>
    <td nowrap="nowrap"><code>plugin_projects_limit</code></td>
    <td rowspan="2"><p>Display limit</p>
<p>Note that <code>plugin_projects_repositories</code> is not affected by this option</p>
<img width="900" height="1" alt=""></td>
  </tr>
  <tr>
    <td nowrap="nowrap"><b>type:</b> <code>number</code>
<i>(0 ≤
𝑥
≤ 100)</i>
<br>
<b>default:</b> 4<br></td>
  </tr>
  <tr>
    <td nowrap="nowrap"><code>plugin_projects_repositories</code></td>
    <td rowspan="2"><p>List of repositories projects</p>
<p>Use the following syntax for each project <code>:user/:repo/projects/:project_id</code></p>
<img width="900" height="1" alt=""></td>
  </tr>
  <tr>
    <td nowrap="nowrap">⏯️ Cannot be preset<br>
<b>type:</b> <code>array</code>
<i>(comma-separated)</i>
<br></td>
  </tr>
  <tr>
    <td nowrap="nowrap"><code>plugin_projects_descriptions</code></td>
    <td rowspan="2"><p>Toggle projects descriptions display</p>
<img width="900" height="1" alt=""></td>
  </tr>
  <tr>
    <td nowrap="nowrap"><b>type:</b> <code>boolean</code>
<br>
<b>default:</b> no<br></td>
  </tr>
</table>
<!--/options-->

## 🔄 Enabling progress tracking

By default, projects have progress tracking disabled.

To enable it, open the `≡ Menu` from the project page and opt-in to `Track project progress`.

![Enable "Track project progress"](/.github/readme/imgs/plugin_projects_track_progress.png)

## 👤 Use personal projects

To create a personal project, select the `Projects` tab from your profile:
![Create a new project](/.github/readme/imgs/plugin_projects_create.png)

Fill informations and set visibility to *public*:
![Configure project](/.github/readme/imgs/plugin_projects_setup.png)

## 📓 Use repositories projects

Repositories projects are created from the `Projects` tab of a repository.

To use it with this plugin, retrieve the last section of the project URL (it should match the format `:user/:repository/projects/:project_id`) and add it in the `plugin_projects_repositories`.

Be sure to tick `Track project progress` in project settings to display a progress bar.

![Add a repository project](/.github/readme/imgs/plugin_projects_repositories.png)

*Example: include a project repository*
```yml
- uses: lowlighter/metrics@latest
  with:
    plugin_projects: yes
    plugin_projects_repositories: lowlighter/metrics/projects/1
```

## ℹ️ Examples workflows

<!--examples-->
```yaml
name: Project from a repository
uses: lowlighter/metrics@latest
with:
  filename: metrics.plugin.projects.svg
  token: ${{ secrets.METRICS_TOKEN_WITH_SCOPES }}
  base: ""
  plugin_projects: yes
  plugin_projects_repositories: lowlighter/metrics/projects/1
  plugin_projects_descriptions: yes

```
<!--/examples-->

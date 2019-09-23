---
title: Comments
---

### Introduction

Being able to add comments to your posts is good for visitor engagement. I have chosen GitHub for hosting comments, as you probably host your website on GitHub anyway. Adding a comment can only be done at the GitHub issue page and requires a GitHub account. These things can be considered as down-sides of using GitHub issues for comments. However, this solution does allow you to fully customize the comment tread with CSS and HTML and to moderate all comments. Additionally, GitHub issues allow commenters to write markdown, automatically escaped code, use custom links, an avatar and their own images. Another plus is that the comments are being stored next to your code, exactly where they belong. Finally, the chosen platform (GitHub) is not known for its data breaches nor for making money from selling visitor data. Make sure to check out the [demo](/blog/gdpr-compliant-comment/).

### How it works

Every comment tread is an issue on GitHub. A call to the GitHub API, using the 'comment_issue_id', retreives a JSON object with all comments. This JSON object is converted into a nice HTML comment tread. The tread is added to the bottom of the (jQuery defined) element in the include. To stay below the rate limit of GitHub, the call is being stored in local storage. A refresh button enables the visitor to force a new GitHub call. Once the rate limit is reached, the visitor has to go to the GitHub issue page to read the comments.

### Installation

Step 1. Create a new issue in your Github repository and look for the issue ID (a number).
<br />Step 2. Add `comment_issue_id: 1` to the front matter of your page (replace '1' by your issue ID).
<br />Step 3. Download the file [comments.html](https://raw.githubusercontent.com/jhvanderschee/jekyllcodex/gh-pages/_includes/comments.html)
<br />Step 4. Save the file in the '_includes' directory of your project
<br />Step 5. Make sure the bottom of your layout document looks like this:

```
{% raw %}...
<script src="/js/jquery.min.js"></script>
{% include comments.html element=".post-content" github_account="jhvanderschee/jekyllcodex" require_cookie_consent="true" %}
</body>
</html>{% endraw %}
```
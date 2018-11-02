---
title: "Comments"
inactive: false
comment_issue_id: 4
---

### Introduction

Being able to add comments to your posts is good for visitor engagement. However, we do not want to send our valuable visitor data to a random surveillance company. Even more so, when the only purpose of that company is to make money from this data and when this company has a bad security reputation. Yes, I am talking about Facebook and [Disqus, owned by Zeta Global](https://www.ghacks.net/2017/12/06/disqus-commenting-platform-sold-to-big-data-and-analytics-firm-zeta-global/){:.gray}. I have chosen GitHub for hosting comments, as you probably host your website on GitHub anyway. This ensures you do not send any additional information to a third party (as all requests already go to GitHub), which makes you GDPR compliant. If you host your website elsewhere, you should make sure that your visitor has approved third party scripts through the [cookie consent banner](/without-plugin/cookie-consent/){:.gray}. I have implemented a 'require_cookie_consent' variable to make this optional. Adding a comment can only be done at the GitHub issue page and requires a GitHub account. These things can be considered as down-sides of using GitHub issues for comments. However, this solution does allow you to fully customize the comment tread with CSS and HTML and to moderate all comments. Additionally, GitHub issues allow commenters to write markdown, use custom links, an avatar and their own images. Another plus is that the comments are being stored next to your code, exactly where they belong. Finally, the chosen platform (GitHub) is not known for its data breaches nor making money of selling visitor data.


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
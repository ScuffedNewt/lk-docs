# Hiring Developers

Often, Lorekeeper owners will find themselves in need of additional development help to build or maintain their site. Whether it's a one-time request or ongoing maintenance, hiring the right developer(s) can make a significant difference in the success of your project.

We recommend reading the [Getting Hired Guide](getting-hired.md) if you're a developer looking to work on Lorekeeper projects. It's also a good resource for project owners to understand what to expect from developers.

If planning on hiring multiple developers, we recommend reading [Working With Multiple Developers](working-with-multiple-devs.md) first and understanding the best practices for collaboration.

## Prerequisites

Before hiring a developer, ensure you have the following in place:

-  Have a clear understanding of what work you want done *before* looking to hire a developer.
-  Make sure you understand what circumstances any potential work is being done under.  
**What does that mean?**
    - Is the work private, or will it become public at some time after completion? When?
    - Check (or ask) up front if the person you’re working with has a Terms of Service (ToS)!
        - If they do, make sure you read and understand it before agreeing to work with them.
        - If they don’t, consider asking them to create one. It protects both parties.

        !!! danger
            Remember that a ToS is not a polite request for people to abide by if they feel like it.
            It exists for the mutual safety of you *and* your developer(s); be ready both to abide by it, *and*, if need be, enforce it.

## Where to Find Developers

1. **Lorekeeper Discord:** The official Lorekeeper Discord server has a community of developers who may be available for hire. You can post in the appropriate channels to find interested parties.
2. **Toyhou.se:** This platform has a section for seeking services.

!!! warning
    Be extremely cautious when hiring developers from third party platforms. Ensure the developer has relevant experience. We personally **do not** recommend hiring developers without prior Lorekeeper experience, as the learning curve can be steep.

## What to Look For
When hiring developers for your Lorekeeper site, consider the following:

- **Experience with Lorekeeper:** Familiarity with the project can significantly reduce onboarding time.
- **Portfolio:** Review their past work to gauge their skill level, particularly if you have tight deadlines or specific requirements in mind. See what other work the person you’re working with has done that is in line with what you’re looking to commission.
    - This can help make sure that potential work done is of good quality, as well as in the vein you’re looking for (depending on the nature of the potential commission).
- **References:** If possible, speak with previous clients for further insight.

## Setting Expectations
Before starting work, ensure that both parties have a clear understanding of:

- **Scope of Work:** Define what tasks need to be completed clearly. Consider using a task management tool to track progress.

- **Access:** Determine what access the developer will need (e.g., GitHub, hosting, etc.)

- **Timeline:** Set realistic deadlines for deliverables.
    - While it’s reasonable to ask for updates, please keep in mind that those you’re working with also have their own lives, and may do other work even in the midst of your commission.
    - Abide by their ToS if it has instructions for this, or otherwise ask after updates about once a week at most frequent (as a baseline).

- **Payment Terms:** Agree on rates and payment schedules.
    - While this might seem obvious for work that costs a flat fee, when dealing with programming work, it’s just as likely that it’s charged at an hourly rate.
    - Make sure you’re aware of which it is, and if dealing with an hourly rate, how long the work will potentially take. In short, get an estimate/ask for a quote!

    !!! warning
        You should do this before committing to anything.

## Giving Developers Access

There are two common ways for a hired developer to contribute to an existing site:

- **Through a shared repository (recommended):** The developer works on a local copy of your site's code and pushes changes to a repository hosted on a service such as GitHub. Changes can be reviewed and tested before you or a trusted maintainer deploys them to the live site. Repository access alone does not give the developer access to your webserver or live database, provided you keep credentials and other sensitive files out of the repository and do not grant deployment access.
- **Through direct server access:** The developer connects to your webserver, usually over SSH, to deploy changes or perform server maintenance. Depending on the permissions granted, this may allow them to change or delete live files, read credentials, and access user data. Changes made directly on the server may also bypass code review and testing.

We strongly recommend collaborating through a shared repository and limiting server access to people who need it for deployment or maintenance. Do not hand over your own SSH credentials as a shortcut to setting up collaboration. If server access is necessary, arrange a separate account with only the permissions required, use the developer's own SSH key, and revoke access when the work is complete. Agree on who will deploy changes before work begins.

### Setting Up a Private Repository

To share your existing site's code on GitHub:

1. Sign in to GitHub and create a new repository by pressing the "+" button and selecting "New repository". Give it a recognizable name, set its visibility to **Private**, and leave it empty so you can push your existing site's history.
2. Copy the repository URL shown after creation, such as `https://github.com/username/repository-name.git`.
3. In your local copy of the site's repository, add that URL as a new remote using your Git client (for example, through the repository settings in Sourcetree). Give it a distinct name such as `github-repo` so you can distinguish it from the live site's remote.
4. Before pushing, check that your site's code and history do not contain secrets or private data, such as `.env` files, SSH keys, database backups, or user uploads. A private repository still exposes its contents to everyone you invite.
5. Push the branch containing your site's current code to the new remote, then check the repository on GitHub to confirm it is present.
   - Sourcetree may prompt you for extra authentication to verify your Github account and that you can access the private repository; it usually tells you what is needed (like a personal access token, sometimes you can just input your account's credentials) and this can generally be googled for a tutorial on setting it up. If you decide to go the PAT (personal access token) route, you can find Github's own information on how to do so [here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens); if using a classic PAT you can input it directly into your repository remote's URL on Sourcetree, i.e. if your PAT is `ghp_12345678910`, you can add it into the URL after the `https://` with an additional `@` before the remainder of the remote URL like `https://ghp_12345678910@github.com/username/repository-name.git` which will allow you to access the private repository with the permissions you set on the token on creation.
6. In the repository settings, invite the developer as a collaborator using their GitHub username or email address. Once they accept, they can clone the repository and propose changes on branches or through pull requests.

For a suggested review and deployment workflow, see [Working With Multiple Developers](working-with-multiple-devs.md).

## Conclusion

Hiring developers for your Lorekeeper project can be a straightforward process if you take the time to prepare and set clear expectations, both for yourself and potential developers.

By following the guidelines outlined in this document, you can find the right talent to help bring your project to life whilst minimizing potential pitfalls.

Contributor Guidelines
These are the general guidelines for contributing to WHATWG standards.

New issues
Please do file these, they are appreciated! Consider reading the FAQ and Working Mode if you are new to standardization.

Participation agreement
Please ensure you, or your employer if you work in the field of web technologies, can sign the Contributor and Workstream Participant Agreement.

If this is your first time contributing to the WHATWG standards, check out the global list of good first issues and find one you want to work on. You should comment in the thread to let others know you will be working on the issue. This is a great time to ask any questions that you may have.

Contributions to older issues are always appreciated. If an issue hasn't been updated in a while, you should ask if the issue is still relevant before working on it. If someone else was previously working on an issue, and you want to work on it, it's polite to ask that person if you can work on the issue before taking it.

Committing
See COMMITTING.md for further details.

Pull requests
Leave the Allow edits from maintainers option enabled to allow reviewers to fix trivial issues directly on your branch rather than needing to write review comments asking you make the edits. For more details, see Improving collaboration with forks in the GitHub Blog.

After you have created a pull request, Javascript and a bot will take care of linking those from your pull request comment (typically within several minutes). These are useful for review and implementing from the standard with the proposed change incorporated.

Building
All WHATWG standards, apart from Javascript, have a Makefile in their repository to help with building them. You'll need make and curl installed at the minimum; ideally you'll also have a full Bash shell. These prerequisites should be present on most Linux and macOS systems already. For Windows, we recommend Git Bash and Make for Windows.

Once you have the prerequisites, you can run make in the standard's directory to build the spec; it will appear as a .html file in the same directory. This will call out to a web service to build the standard, so be sure you're connected to the internet.

Other Make targets are also available:

make deploy will do a full "deploy" of the standard, including error checking, commit snapshot production, any extra build steps, into a local subdirectory.
make local will do a local build, without calling out to any web services. This requires having Bikeshed installed locally.
Due to its large size, the HTML Standard has its own build process, which you can read about in the html-build repository.

Tests
For normative changes, a corresponding web-platform-tests pull request (PR) is needed. The author and reviewer can be different from the PR for the standard. If current behavior is unclear, writing tests first can help inform the discussion. Typically, both PRs will be merged at the same time.

To be clear, a test PR with changes that conflict with the standard cannot land before the corresponding standard is changed.

If testing is not practical, please explain why and if appropriate file an issue to follow up later.

Investigation
Often in the course of discussing a potential change, issue with a standard, or browser bug, it's useful to investigate the behavior in question in a variety of rendering engines and provide data back to the discussion. The best way to do this is to host a small test case and report the results in various engines.

For simple cases (not involving multiple files), sites like Live DOM Viewer or JSBin are recommended. For cases involving multiple files, you'll likely need to use your own hosting, for example using GitHub Pages. Or you could skip straight to working on web-platform-tests, as discussed above.

Attempt to make your test cases produce clearly-differentiable results regarding the different outcomes you're investigating. You can then report the results back to the issue thread using the following Markdown syntax as a starting point:

| Test case                               | Blink | Gecko | WebKit |
|-----------------------------------------|-------|-------|--------|
| Test case description 1                 |       |       |        |
| Test case description 2                 |       |       |        |
| Test case description 3                 |       |       |        |
If there are additional interesting engine variations you are testing, for example older versions or engines not in the list, feel free to add more columns. If you can't test certain engines, leave a question mark in that cell, and others on the thread can help fill them in.

For examples of this kind of investigation in action, see whatwg/html issue #775 or whatwg/html issue #1087.

Further principles and guidelines
For any changes please take into account the following principles and guidelines:

Javascript Design Principles (note that these are applicable outside of HTML too and you are expected to treat them as such)
Client-side API Design Principles
WHATWG Working Mode
WHATWG FAQ, in particular Is there a process for removing bad ideas from a standard? and How should I go about proposing new features to WHATWG standards?
Downstream impact
If you change exported definitions or algorithms, Webdex allows you to evaluate the impact of your change on other specifications. If any are impacted please do notify them by filing issues or creating pull requests.


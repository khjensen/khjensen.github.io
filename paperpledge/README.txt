THE ONE PAPER PLEDGE — SETUP

1. Set the organiser email
Open index.html in a text editor. Find:
  const ORGANISER_EMAIL = '';
Replace the empty string with the real organiser email address, keeping the quotes.
Until configured, the page explains that an address is needed and offers copying.
No backend, email service, analytics, cookies, or external dependencies are used.
Email signup opens the visitor's email app; the visitor must send the request.

2. Add approved signatories
Review incoming requests and their consent before publishing details.
Edit signatories.txt as UTF-8 plain text. Keep the header exactly as delivered.
Each subsequent line has four columns separated by literal TAB characters:
  name [TAB] institution [TAB] country [TAB] date_signed
Use YYYY-MM-DD for signing dates. Leave optional columns empty, retaining tabs.
Use one row per approved person. Do not put tabs or line breaks inside fields.
Do not include email addresses in this public file. Check for duplicate requests.
The website calculates the count and sorts names automatically. Search covers
names and institutions. Invalid rows produce a helpful file-loading message.
The date in the request uses the visitor's local calendar date; verify it when
reviewing. Keep request emails securely in the organiser's own email system.

3. Host both files together
Upload index.html and signatories.txt into the same directory on any static
HTTP/HTTPS host. No build step or installation is necessary. Ensure the server
serves signatories.txt as a real text file rather than redirecting it to HTML.
HTTPS is recommended and enables the Clipboard API in supported browsers.
After updating the public text file, reload the page to see the new directory.

For a local preview with Python 3, run this from the folder containing both files:
  python3 -m http.server 8000
Then visit http://localhost:8000 in a browser.
Opening index.html directly also works: use the directory file picker to load
signatories.txt. Automatic clipboard access may be restricted; the page then
selects the request text and gives manual copying instructions.

The native dialog provides keyboard focus containment and Escape to close.
The form keeps details in the page's memory only. Closing it preserves a draft
until the page is reloaded; it does not send, publish, or save the request.

PLEDGE TERMS
The one-paper ceiling applies to original research papers arising primarily
from the signatory's own research ideas. Collaboration on additional papers
arising primarily from the ideas of others remains welcome. Shared origins
are interpreted in good faith, without formal accounting or monitoring.
The signup consent and prepared email use these revised terms.

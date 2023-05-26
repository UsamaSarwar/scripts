# Bulk Withdraw Connection Request on Linkedin
JavaScript code that you can run in the console of Google Chrome to achieve your desired task.

Please follow the steps below:
1. Open the Google Chrome browser and navigate to the LinkedIn page: https://www.linkedin.com/mynetwork/invitation-manager/sent/
2. Right-click on the page and select "Inspect" or press Ctrl+Shift+I (Windows/Linux) or Command+Option+I (Mac) to open the Chrome Developer Tools.
3. In the Developer Tools panel, click on the "Console" tab.
4. Copy and paste the following code into the console:

```bash
function withdrawAllInvitations() {
  const withdrawButtons = document.querySelectorAll('button[aria-label^="Withdraw invitation sent to"]');
  
  withdrawButtons.forEach((button, index) => {
    setTimeout(() => {
      button.click();
      setTimeout(() => {
        const withdrawConfirmButton = document.querySelector('button[data-test-dialog-primary-btn]');
        if (withdrawConfirmButton) {
          withdrawConfirmButton.click();
        }
      }, 2000);
    }, index * 3000);
  });
}

withdrawAllInvitations();
```
5. Press Enter to run the code.

This script will find all the "Withdraw" buttons on the page and click them one by one. After clicking each button, it will wait for 2 seconds and then click the confirmation button in the popup. It repeats this process for each invitation on the page.
Please note that running scripts in the browser console can interact with web pages and perform actions on your behalf. Make sure you understand the code and trust the source before executing it. Also, keep in mind that LinkedIn's terms of service may prohibit or limit automated actions like withdrawing connection requests. Use this script responsibly and at your own risk.

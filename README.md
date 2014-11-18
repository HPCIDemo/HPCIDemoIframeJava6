HostedPCI Demo Iframe for Java 6 October 6 2014

What is it?

———————————

The HostedPCI Demo Iframe app is a small tool to help HostedPCI customers visualize the power, potential and how HostedPCI can help them become PCI compliant as affordable as possible and as easy as possible. Our motto is, your vision, our reality.
By installing HostedPCI Demo Iframe you will see what it can do for you, how easy it is to implement it on your eCommerce site and will show you how to do it if you get stuck implementing it.

How does it work?

————————————————

1. eCommerce loads the page.
2. Page requests a new iframe from HostedPCI.
3. HostedPCI verifies the website and webpage are correct.
4. HostedPCI sends the iframe to the eCommerce page.
5. User fills the payment form and clicks “Submit”.
6. Iframe is being sent back to HostedPCI for tokenization of the credit card.
7. Token is delivered back to the form and populates all the required hidden fields (CC, CVV and BIN numbers) in the form.
8. eCommerce form submits payment request with credit card token, cvv token, expiry date and amount.
9. HostedPCI submits payment request with real credit card, real cvv, expiry date and amount.
10. HostedPCI gets the payment response from the bank.
11. HostedPCI sends the response along with other information back to the eCommerce site.
12. eCommerce page can then collect the response with all the information and display it back to the user.

Release Version

——————————————

1.0 Oct 6 2014

Further details can be found at http://www.hostedpci.com

Prerequisites 

————————————

Java JDK 1.6
Browser
Terminal/Command Prompt
HPCIDemoIframeJava6.war and Jetty-runner.jar (can be downloaded from www.hostedpci.com)

Installation

———————————-

MacOs: 

1. Download HPCIDemoIframe.war and Jetty-runner.jar and place them in the same folder.
2. Open terminal and go to the folder you placed the two files.
3. Type “java -jar jetty-runner.jar --stats unsecure --log yyyy_mm_dd-requests.log --port 8799 --out yyyy_mm_dd-output.txt HPCDemoIframeJava6.war”
4. If everything went well, you should see something like this and a blinking cursor afterwards:
2014-10-08 10:33:36.843:INFO::main: Logging initialized @71ms
2014-10-08 10:33:36.848:INFO:oejr.Runner:main: Runner
2014-10-08 10:33:36.850:INFO:oejr.Runner:main: Redirecting stderr/stdout to yyyy_mm_dd-output.txt
5. Open any browser and type in: localhost:8799/DemoIframe/ or 127.0.0.1:8799/DemoIframe/
6. Fill in the payment form, you can use dummy visa number 4111 1111 1111 1111 cvv: any 3 digits, Expiry date must be date in the present or date in the future.

FAQ

———

1. If you want to use a different port (not 8799) the file form.jsp has to reflect that change inside the iframe in 2 places, for example:
src="https://cc.hostedpci.com/iSynSApp/showPxyPage!ccFrame.action?pgmode1=prod&locationName=javasample1&sid=528160&fullParentHost=http://localhost:8799&fullParentQStr=/form.jsp” 
Needs to become: 
src="https://cc.hostedpci.com/iSynSApp/showPxyPage!ccFrame.action?pgmode1=prod&locationName=javasample1&sid=528160&fullParentHost=http://localhost:9090&fullParentQStr=/form.jsp”
Assuming port was changed from 8799 to 9090.
2. Logs can be seen inside the directory where HPCIDemoIframeJava6.war and Jetty-runner.jar are found. For example:
2014_10_08-requests.log has the request logs
2014_10_08-output.txt has the standard output and error
3. Interesting stats can be seen in the browser at localhost:8799/stats/
4. Must have JDK installed, doesn’t work with JRE.

Contacts

————————

HostedPCI Inc.
http://www.hostedpci.com/
sales@hostedpci.com
1-866-850-3608

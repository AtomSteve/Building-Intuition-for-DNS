<p align="center">
<img src="https://github.com/AtomSteve/Building-Intuition-for-DNS/assets/147112183/6f25c1e8-ef5d-403f-9ad1-c11a3bbb5581" width="400" height="350" />


<h1>Building-Intuition-for-DNS</h1>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory
- Command Line

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2> Objective Exercises</h2>

-  A-Record Exercise
-  Local DNS Cache Exercise
-  CNAME Record Exercise


<h2>A-Record Exercise</h2>
Log/Connect into DC-1 with your domain account and do the same with Client-1.  Open Command-Line and ping "mainframe" it should come back with nothing, also do Nslookup "mainframe" notice it will also fail.  Now go to Server manager -> Tools -> DNS -> DC1 -> Forward Lookup Zone -> mydomain.  Now in my domain create a New Host (A or AAAA) record.  Put the IP Address at whatever you want, ill use DC-1 ip address.  Ping mainframe to make sure it works.  


</p>
<p>

![image](https://github.com/AtomSteve/Building-Intuition-for-DNS/assets/147112183/165bbd38-225a-4627-85b5-314fb5375bd3)![image](https://github.com/AtomSteve/Building-Intuition-for-DNS/assets/147112183/fc890080-c266-4315-8c2b-9bfacc05022e)![image](https://github.com/AtomSteve/Building-Intuition-for-DNS/assets/147112183/419c7366-1c2e-4785-8cb5-e7e382e24d65)

</p>

<h2>Local DNS Cache Exercise</h2>

Now that mainframe is working go ahead and change its ip address to 8.8.8.8.  Go back to client-1 and ping mainframe again, notice that it still shows the old ip adress, what need to be done is we need to flush the dns cache.  run command line as administrator and typ (ipconfig /dispalydns) to get rid of all the cache you need to type the command (ipconfig /flushdns).  Notice that the cache is now empty.  Once you ping the mainframe once more you will notice the updated ip adress


</p>
<p>

![image](https://github.com/AtomSteve/Building-Intuition-for-DNS/assets/147112183/2be90333-9b91-445a-96f5-88bc0fa06c6a)![image](https://github.com/AtomSteve/Building-Intuition-for-DNS/assets/147112183/d1d95ccd-2475-4927-8b82-7807d5a428d9)

</p>

<h2>CNAME Record Exercise</h2>

On DC-1 go back to server manager under tools to DNS and next to mainframe creat a "New Alias (CNAME).  Name it search and accociate it with a random website like www.google.com.  Now when you ping search on command it will now pull up google.com.   

</p>
<p>

![image](https://github.com/AtomSteve/Building-Intuition-for-DNS/assets/147112183/e22c9adf-5282-4c56-bb77-afac0f6adb7c)![image](https://github.com/AtomSteve/Building-Intuition-for-DNS/assets/147112183/15e95376-d105-4593-9f4b-5b5df3931e78)







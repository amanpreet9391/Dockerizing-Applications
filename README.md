# docker-images
import os
import subprocess
import getpass
import user
os.system("tput setaf 1")
print("\t\t\twelcome to my tool")
os.system("tput setaf 0")
print("\t\t\t-------------------------"
)
actual_password="aman9391"

input_pass=getpass.getpass()
if actual_password!=input_pass:
	print("not authorised ")	

else:
	while(True):
		os.system("clear")
		print("where do you want to execute (local/remote): ",end=" ")
		ch_platform = input()
		print(ch_platform)
		if ch_platform=="local":

			print("""
			press 1:to check date
			press 2:to check cal
			press 3:to check ls
			press 4:to create user
			press 5:to create file
			press 6:exit
			""")
			print("enter ur choice :", end=' ')
			ch=input()
			print(ch)
			if int(ch) == 1:
				output=subprocess.getoutput("date")
				print(output)
			elif int(ch) ==2:
				output=subprocess.getoutput("cal")
				print(output)
			elif int(ch) ==3:
				output=subprocess.getoutput("ls")
				print("list of files in the folder containing python script")
				print(output)
			elif int(ch) ==4:
				user.user_create()
			elif int(ch) ==5:
				file_name=input()
				file_create="gedit {}".format(file_name)
				output=subprocess.getstatusoutput(file_create)
				if(output[0]==0):
					print("file created successfully")
				else:
					print("error in creating file")
			elif int(ch)==6:
				exit()
		elif ch_platform=="remote":
	
			print("IP of remote : ",end=" ")
			remote_ip=input()	
			print(remote_ip)
			print("""
			press 1:to check date
			press 2:to check cal
			press 3:to check ls
			press 4:to create user
			press 5:to create file
			press 6:exit
			""")
			print("enter ur choice :", end=' ')
			ch=input()
			print(ch)
			if int(ch)==1:
				x=subprocess.getoutput("ssh {} date".format(remote_ip))
				print(x)
			elif int(ch)==2:
				output=subprocess.getoutput("ssh {} cal".format(remote_ip))
				print(output)
			elif int(ch)==3:
				out=subprocess.getoutput("ssh {} ls".format(remote_ip))
				print(out)
			elif int(ch)==4:
				print("Enter username :",end=" ")
				user_name=input()
				x=subprocess.getstatusoutput("ssh {} useradd {}".format(remote_ip,user_name))
				if (x[0]==0):
					print("user added successfully")
				else:
					print("error!!")
			elif int(ch)==5:
				print("enter name of file to be created :",end="")
				file_name=input()
				x=subprocess.getstatusoutput("ssh {} gedit {}".format(remote_ip,file_name))
				if (x[0]==0):
					print("user added successfully")
				else:
					print("error!!")
			elif int(ch)==6:
				exit()
		else:
			print("not found")
		input("enter to continue")


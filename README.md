# ftandchat
The TELCO Central Exchange (The Company) in Suva, Fiji is connected to more than 200 Sub Exchanges (Clients) with 64 Kbps Leased Lines. Entire TELCO is using Oracle Runtime Reports (.fmx extension) in their day-to-day operations. They are having a separate Oracle Server and NMS Server (FTP) for operations. The The Company supplies the reports to the Clients, and whenever they open the Report, the Version Number of the Report should be matched in the Oracle Server. Each Report will have its own Version Number, and it will change whenever the Report is upgraded. In that situation new Reports have to be supplied to the Clients. For that they are using the NMS Server, which is a central store of data, and they keep the recent Reports in some directory. The Clients have to download the reports in some specified directory, whenever their Reports will never be opened. 
	The Problem is that the Personnel in Sub Exchanges are not much trained to download or upload the files from FTP Server.
	The proposed system to solve the problem is that, a Server program, which always in Listening state keeps track of all clients that are connected to the Server.Any client, can send a file or message directly to other client(s) to the specified directory, and finally it receive the acknowledgement. Server acts as a mediator and simply redirects the files from sender to receiver. The clients are identified by their IP Addresses.
	This is a User Friendly Package, and will have 2 modes of clients, Active and Passive. The ‘Sending’ option is been restricted to the Passive clients, and they can only receive the files. Active Clients (The Company) can Send/Receive files. The Clients (probably of Passive mode) can be disconnected explicitly after once the acknowledgement of ‘File Transferred’ is received. Not only .fmx files, any kind of files can be sent using this System. 


			INTRODUCTION TO ENVIRONMENT

	This Package has been developed in Java of version 1.3, which is based on Object Oriented Methodology. There are several packages resided in Java and to develop this system, mainly networking, swing packages of Java are used. Various features of Java made it a first choice of the programmers. Java is a platform independent language, which can be run under any kind of environment.

The main features involve,
1.	Simple: - Java is a language which is based on Object Oriented Methodology, so it is very easy to learn and can be used effectively.

2.	Robust: - Java Programs are said to be robust because they will take care of memory management and will never crash under any circumstances.


3.	Secure: - Even though Java is developed using Object Oriented Principles, it eliminated the Pointers Concept. So it is not possible to access memory directly, that’s why Java is said to be Secure and is applicable for Internet, for that Applet is designed which can be understandable by the browsers.

4.	Portable: - Java Programs are Portable that those can be run under any kind of environment irrespective of the hardware used. This is known as platform independent.


5.	Compiled & Interpreted: - Unlike remaining Programming languages Java code is both Compiled and Interpreted. The output after compilation is ‘Byte Code’ which is interpreted to produce output. This Byte Code is a new evolution, which makes Java a Platform Independent Language.



Software Used: - Some of the features of Java that are used in this system include,
Multithreaded programming that allows running 2 or more processes concurrently.
The Server program is implemented using this concept so that it will always be in listening state.

Packages Used: -

1.	The default package to build any program in Java is lang that is used in developing this system
2.	The API to build Graphical User Interface in Java is provided using the packages awt and swing. This system uses both the packages to provide GUI based forms.
3.	To provide the communication over the network, the package net is used to develop the Server and Clients.
4.	In Java JDBC (Java Database Connectivity) is used to connect to the database, a special package known as sql is developed for that. 
5.	The util package in Java is an enhancement of the existing classes. This package is also used in this system for declaring arrays (Vector), and to manipulate the strings.
6.	 The streams that are used to send and receive the data over network are also utilized in this system, which are in the package of io. 


Hardware Used: -  

Server side: - The Server program must be as fast as possible to keep track of all the connected clients, and the memory must be as much as sufficient. The Systems which were kept as Oracle Server and NMS Server are having high speed processor and a large capacity of RAM (Random Access Memory). The Server program has to be placed in the NMS Server that is very fast and can handle any number clients.
Some of the configuration is listed below,

Console: -     	        Mouse, 15” Monitor, 104keys Keyboard
Processor: - 	        Intel Pentium IV processor, 1.9 GHz speed.
Memory: - 	        256MB RAM, 40GB Hard Disk.
Cache: - 		        56MB.
Ports: - 		        Serial Ports, Parallel Ports (LPT-1, LPT-2)
N/w Components: -  Network Adapter, RJ-45 Connector, HUB.

Client side: - The Client program doesn’t need high-speed processor, RAM like Server. The minimum configuration is needed to install the Client program.
Some of the configuration is listed below,

Console: -                    Mouse, 15” Monitor, 104keys Keyboard
Processor: -                  Intel Pentium III/IV processor, 1.1 GHz speed.
Memory: -                    64/128 MB RAM, 40GB Hard Disk.
Cache: - 		            56MB. 
Ports: -                          Serial Ports, Parallel Ports (LPT-1, LPT-2)
N/w Components: -      Network Adapter, RJ-45 Connector, UTP 
                                      Cable, HUB.


Requirements Analysis
	
Requirement Analysis is done to understand the problem the software system is to solve. The emphasis in requirements analysis is on identifying what is needed from the system, but not how the system will achieve the goals. This involves 2 phases,

1.	Problem Analysis

2.	Requirement Specification


Problem Analysis: -The basic aim of Problem Analysis is to obtain a clear understanding of the needs of the clients, i.e. what exactly is desired from the software, what are the constraints to be imposed while developing. After this phase the analyst will get a clear idea about the project.
 Since the system is developed using Objected Oriented Paradigm, the needs of the clients are shown as Scenarios and Use cases. Some are listed below,


1.	Use case & Scenario for the need to connect to the Server.




Initiator                                                                                                Initiator
(User)	(User)



Precondition: - Here the Initiator is some personnel in the department, who wants to send a file or a message to some other client.

Actor Initializing: - A department personnel (One client)

Steps: - 1. The User connects to the Server to send a file or a message.
   2. The User selects another client to whom he wanted to send 
        a file or message.
	   3. Exit.

Post condition: - The user gets connected to the Server.




2.	Use case & Scenario to transferring file to single/multiple client(s).



Initiator                                                                                                 Initiator
(User)	 (User)



Precondition: - Here the Initiator is the user, who wants to send a file to a single client or multiple clients.

Actor Initializing: - A department personnel (One client)

Steps: - 1. The user first connects to the Server.
  2. The user can select a single client or multiple clients to transfer
       a file simultaneously.
	  3. Exit

Post condition: - The user gets the acknowledgement that the file has been reached.



3.	Use case & Scenario for specifying the paths.


Initiator                                                                                                 Initiator
(User)	 (User)



Precondition: - Here the Initiator is a client, who wants to send a file.

Actor Initializing: - A department personnel (One client).

Steps: - 1. The User connects to the Server to send a file or a message.
	   2. The User selects another client to whom he wanted to send a file.
	   3. The User has to give the source path and the destination path
                  correctly.  
             4. Exit.

Post condition: - The Specified file will be transferred to the specified location if exists, in the remote system, if not ‘Path not found’ message has to be displayed.


4.	Use case & Scenario to disconnect a single/multiple client(s).


Initiator                                                                                                 Initiator
(User)	 (User)



Precondition: - Here the Initiator is the user, who wants to disconnect a single or multiple clients.

Actor Initializing: - A department personnel (One client).

Steps: - 1. The user first connects to the Server.
   2. The user can select a single client or multiple clients to disconnect
      at a time.
  3. Exit.

Post condition: - The user’s presently connected clients list will be updated.


FEASIBILITY STUDY

 	This phase is done as part of the Preliminary Investigation and the important outcome of this phase is the determination that the proposed system is feasible or not in all aspects. Various aspects involve whether the proposed system is Technically, Operationally, Economically feasible or not.  The goal of the feasibility study is to determine whether a proposed project is worth pursuing. This study examines two fundamental categories: Costs and Benefits.

Technical Feasibility: - In order to establish the proposed system in the real environment, it is not needed to go for further technology. The existing technology is sufficient to maintain the proposed system. For example, the NMS Server that is having a very high capacity can be used as Server for the desired System. So that we can say that the proposed system is technically feasible.

Operational Feasibility: - There is sufficient support for the project from the TELCO personnel and users. The proposed system will not cause any harm, and doesn’t give poor results in any respect areas. The personnel are having a greater requirement of this system and hence we can say that proposed system is operationally feasible.
 
Economical Feasibility: - Since TELCO is a very big government organization and can bare any kind of cost. Even though, to establish the proposed system no need of special hardware/software. No need of licensing the Java Software (JDK) to launch this system, because JVM (Java Virtual Machine) is distributed with Oracle Forms 6i. So making use of this, the proposed system can work. Hence we can say that the proposed system is Economically Feasible. As part of the economic feasibility, Cost Benefit Analysis has to be done to determine the proposed system is feasible or not.


COST- BENEFIT ANANLYSIS: - In this analysis we observe what the various costs are involved and what are the potential benefits related to the costs. If the total cost becomes more than the benefits, then there is no gain from the proposed system and the proposed system is not feasible. If total cost is less than the benefits then we can say that the proposed system is feasible. The costs are estimated with the help of vendors. Some of the costs and benefits that are identified in the Cost-Benefit Analysis are listed below,

Costs: -  
•	Up-front/One-time costs: -   

	Software
	Hardware
	Communications
	Data Conversion
	Training
	
•	Ongoing costs: -

	Personnel
	Software Upgrades
	Supplies
	Support
	Software and Hardware Maintenance

          The proposed system doesn’t require any of the costs above specified, because all are already established in the Central Exchange, so no need for additional costs.


Benefits: -
		There are several benefits involved after once the proposed system is operational. Some are listed below,
•	Cost Savings: -

	Software Maintenance
	Fewer errors that will occur in this system
	No training is required to personnel
	Better Communication
	Better Access of Data

 	Because of all these benefits involved in the proposed system, which is having more benefits than costs, we can say that the proposed system is feasible.

		(Benefits > Costs)    Proposed System is Feasible


PREPARATION OF REQUIREMENT SPECIFICATION

	The final output of the Requirement Specification is Software Requirements Specification document (SRS). Problem Analysis generally focuses on the problem structure, not its external behavior. So some of the things for the user interface should be modeled, which are major components of the SRS. The aspects in the SRS will be useful to the Designer to design the proposed system.

Software Requirements Specification (SRS): - 

	Major Components that involved in SRS are,

•	Functional Requirements

•	Performance Requirements

•	Design Constraints


Functional Requirements: - 

1.	It is only possible to connect to the server whenever it is under running. If the server is running, then any number of clients can get connected.
Validation: - After once a client connected to the server then it is not possible to connect again to the server.

2.	In order to send a file then enter the Source & Destination paths must be entered correctly.
Validation: - If the Source path is entered wrong or not entered, then an error should be displayed. If the Destination path is wrong then the client has to be intimated by the server that the path doesn’t exist in the remote client.

3.	To disconnect a single client or multiple clients, choose the clients and disconnect. After disconnect observe that whether the clients are in the connected clients list or not.

Performance Requirements: -

The Performance of the Server is not constant. It is depend upon the network constraints, the hardware configuration of the Server. If less than 50 clients are connected to the Server then the burden on server is less. If more than 50 clients are connected then the burden will increase.
The remedy to the problem is simply disconnecting some of the clients whose are in passive state.

The response time will also be considered to assess performance, which is also depending upon the network constraints, and the hardware configuration of Server.


Design Constraints: -

	There are number of factors in client’s environment that may restrict the choices of a designer. Such factors include,

1.	Standards Compliance: - The basic standard for the proposed system is that the Server should never crash under any circumstances.

2.	Hardware Limitation: - There is no hardware limitation to be specified.

3.	Reliability and Fault Tolerance: - The proposed system should be highly reliable and must be fault tolerant. Probably there will not be any fault, and if any fault occurs then better to restart the Server.


4.	Security: - The existing system is highly secured, and no further security is needed for proposed system.



Software Design

OBJECT ORIENTED DESIGN METHODOLOGY

Introduction: - Design is concerned with the mapping of objects in the problem space into objects in the solution space and creating an overall structure of the system. 
The Object Oriented Design Methodology involves the following steps:

1.	Review of Objects created in the analysis phase
2.	Specification of class dependencies
3.	Design of classes
4.	Identifying the class dependencies

The best approach for Object Oriented Design is Unified Modeling Language (UML). The UML model describes what a system is supposed to do. It doesn’t tell how important the system. Various tools are used to present multiple views of the system. The UML enables system builders that create blueprints that capture their visions in a standard, easy-to-understand way and communicate them to others.




 Activity Diagrams: -

	Activity Diagram shows the overall functionality of the system.

1.	Activity Diagram for Connecting to the Server.



           

                                             
                                 IP Address			Update the List







2. Activity Diagram for getting the information of a client (Identity of a client).





















2.	Activity Diagram for transferring file.


















	If path exists	If path doesn’t exist 




                                                                                                     
















4. Activity Diagram for Disconnecting (Active/Passive mode) clients.






































Sequence Diagrams: -

	Sequence diagrams are used to represent the sequence of events basing on the time, i.e. these show the time-based dynamics of the interaction.

1.	Sequence Diagram for Clients that connect to the Server.



                  Client 1 Connects
	      
                    Updates Client 1			
	Client 2 Connects
	Updates Client1
	Updates Client 2
	Client 3 Connects	

	  Updates Client1
	Updates Client 2

	Updates Client 3






















2.	Sequence Diagram for transferring a file from Client 1 to Client 3. Here client 3 is a passive mode client, which can only receive a file/message.





	      
                    			
	




	Selects a file 
               And sends it to the
               Client 3.
	Server redirects the        file to Client3





















3.	Sequence Diagram for Implicitly disconnecting a single or multiple clients. Here client 3 is passive mode client, which can only receive a file/message.




	      
                    			
	




	Sends a message
                To disconnect
	Client 3.	Server Disconnects        Client 3 forcibly

                  Updates Client 1
	Updates Client 2
















Class Diagrams: - The things naturally fall into categories we refer to those categories as classes. A class is a category or group of things that have similar attributes and common behavior.

1. Class Diagram for a Client.












2. Class Diagram for Server.






















Object Diagram: - An Object is an instance of a class. A specific thing that has a specific value of the attributes and behavior.


1.	Object Diagram for Client.




2.	Object Diagram for Server.



3.	The Relationship among Server and Clients can be represented using the object diagram.


























State Transition Diagrams: - 
At any given time an object is in a particular state. State Transition Diagrams are used to represent the states of an object at any particular instance.

1. State Transition Diagram for Server.





	Sends Host Address




	Client gets updated




	Client Exited





	













DATABASE DESIGN

INTRODUCTION: -

            In this phase the actual database is designed, which is used for,

1.	Structuring the data

2.	Identifying the entities

3.	Showing the relationship among entities

Structuring the data is nothing but normalising the data. Normalisation is the process of simplifying the relationship among the data elements in a record. 

Various aspects involve that whether the database is distributed or not, which database should be used by considering the organization.
Presently the organization is using the Oracle Server. So the database of the system to be developed is Oracle. 

E-R Diagram: -

               E-R Diagrams are used to represent the relation ship among the entities. In this system there are only 2 entities that are Server and Client. So the Entity Relationship Diagram for this system is drawn below,

	 	


				1…1		      1…*	
	










Normal Forms Implemented: -

Normalisation process is carried out for four reasons,

	Structure the data to pertinent relationships.

	To permit simple retrieval of data in response to query.

	Simplify the maintenance of data through updates insertions and deletions.

	To reduce restructuring or organize the data.

Here in this system only one table is used which is having 2 fields. The table is already in First Normal Form. So no need to normalize here. Even though, some of the normalisation process has been given below,

First Normal Form: - A table is said to be in First Normal Form after eliminating the repeating groups of data and putting them in a separate table.

Second Normal Form: - Every non-key attribute must fully functionally dependent on the primary key. If not, put the column in a new table along with the portion of key.

Third Normal Form: - To reach 3NF, check whether the non-key column depends on anything that is not in the key. If so, pull out the column and the dependent column and put them into a new table.


















Table description: - 
	The Table ‘users’ is having only 2 fields that are client name and IP Address.
This table is designed to map the client name with its IP Address.

Field Name		    Data type
1. Clientname		Varchar (30)    (not null)
2. IPAddress		Varchar (16)    (not null)

























TESTING


Introduction: - In a Software development project, errors can be injected at any stage during development. In Testing phase, the program to be tested is executed with a set of test cases and the output of the program for the test cases is evaluated to determine if the program is performing as expected. Testing is the process of executing a program with the intent of finding errors.
There are 2 basic approaches for testing: functional and structural. In functional testing the structure of the program is not considered. Test cases are decided solely on the basis of the requirements specification of the program or module and internals are not considered for selection of test cases. Due to its nature, functional testing is often called Black Box testing.

For testing purpose the test cases are designed in the following format.

Condition: -xxxxxxxxx
Input Criteria: -xxxxxx
Input: - xxxxxxxxxxxx
Result: - xxxxxxxxxxx

The condition describes the rule of the system.
Input criteria specify the valid input boundaries.
Input defines the sample input.
Result gives the output of the sample input.













Black Box Testing

Introduction: -Black Box testing doesn’t consider the structure of the program; hence the test cases that used for Black box testing are,

Source:  ActiveForm, Ftpser

1.	Test case for ‘Server should run for a client when a client want to connect to the Server’.

Condition:  “The Server must be under running state when a client get
                        Connected”.
Input Criteria:  Any client can connect to Server, which is not running.
Input:  Client 1 wants to connect.
Result: Error message “Server Presently Not Running” is displayed.

Source: ActiveForm, Ftpser, PassiveForm

2.	Test case for ‘A client wants to connect twice to the Server’.

Condition: “A Client should not be connected twice to the Server”.
Input Criteria: Allow any client connect to the Server twice.
Input: Client 1 is already connected to the Server, and wants to connect 
             again.
Result: Error message “You are already connected to the Server” is 
              Displayed.


















Source: ActiveForm, Ftpser,PassiveForm

3.	Test case for ‘A client should be disconnected from the Server, even the client program is terminated abnormally’.

Condition: “ A client has to be disconnected when it is terminated abnormally”.

Input Criteria: Take any client.

Input: Terminate the client program in any way (normally or abnormally).

Result:  The particular client is disconnected from the Server.





















White Box Testing


Introduction: -The Structural approach is also known as White Box testing.
 In this approach test cases are generated based on the actual code of the program or module to be tested. This Structured approach some times called as “Glass Box testing”.
Some of the test cases are listed below,

Source: Form

1. Test case for “Entering source and destination paths accurately”.

Condition: “ The Source and destination paths must be entered”.
Input Criteria: Choose any client to transfer a file.
Input: do not enter source path.
Result: Error message ‘Paths Should be entered Correctly’ is displayed.

Source: Killall

2. Test case for “Disconnecting single/multiple clients”.
Condition: “ Clients can be disconnected from the server forcibly by 
                       Another client”.
Input Criteria: Choose single or multiple clients.
Input: Client 1 is selected.
Result: Client 1 is removed from the “Connected Users Information” form.
























Source: ActiveForm

3. Test case for “Transferring a file to a single or multiple clients”.

Condition: “Clients can send a file to one or more clients”.

Input Criteria: Choose single or multiple clients.

Input: Client 1 is selected.

Result: A message “File transferred to system: Client 1” is displayed in the 
             Status box.



















FORMS DESIGN
	
	This is a User-friendly system and hence there will be less involvement of the user with respect to giving input.

Input Design: -The main Objectives of Input Design are,

	Controlling the amount of input
	Avoiding the delay
	Avoiding the errors in data entry
	Avoiding the extra steps
	Keeping the process simple

Output Design: - The main Objectives of Output Design are,

	To assess efficiency of the system.
	 Getting the status of the system.
	 Information Service.
	 Knowing the effectiveness of the system.

This Stage identifies the following input and output areas,
					ActiveForm	
					PassiveForm
					Chat
					Sendall
					Killall
					ClientForm
          	Form			
	Chatform











DESCRIPTIONS: -

Source: ActiveForm

Title: “Connected Users Information”.
User:  Any Active Client.
Frequency: Each client once.
Contents: 	ClientsIP	(L)
		Status		(ML)
		Kill		(B)
		Sendall	(B)

Source: Sendall

Title: “Sending to Group”.
User: Any Active Client.
Frequency: Infinite.
Contents:	ExistingClients	(ML)
		SelectedClients	(ML)
		Selectall		(B)
        

Source: Chat

Title: “Connected Users Information”.
User:  Any Active Client.
Frequency: Each client once.
Contents: 	ClientsIP	(S)
		Status		(ML)
		Sendall	(B)

                               









Source: Form

Title: “File Transfer to Client:”
User: Any Active Client
Frequency: Infinite.
Contents:	Sourcepath	(A)
		Destpath	(PA)
		Status		(ML)

 Source:  Chatform 

Title: “The Sender:”
User: Any Active Client
Frequency: For single/multiple Clients
Contents:	Message	(T)
		Whole	(ML)
		Send		(B)

Note:

A  Automatic
PA  Partial Automatic
T  Text
ML  Multi Line
B  Button
S  Selection












IMPLEMENTATION/USER INTERFFACE

INTRODUCTION: -When the System is operational in to the user environment, there might have a change of getting errors in real environment. Then the same process will recur until the desired system is achieved.

Maintenance involves performing any one or more of the following three kinds of activities:

     1. Correcting errors that were not discovered during the product 
Development phase. This is called Corrective Maintenance.

2.Improving the implementation of the system and enhancing the      functionalities of the system according to the customer’s requirement. This called Perfective Maintenance.

3.Porting the software to a new environment. This is called 
Adaptive Maintenance.























INSTALLATION CHECKLIST

1.HARDWARE: -

This specifies the minimum requirements of Hardware that is needed to install the System.

      The minimum requirements for Server.

Console: - 		       Mouse, Monitor, 104keys Keyboard
Processor: - 	        Intel Pentium III processor, 1.1 GHz speed.
Memory: - 	        128MB RAM, 20GB Hard Disk.
N/w Components: -       Network Adapter, RJ-45 Connector, HUB.

The minimum requirements for Client.

Console: -                    Mouse, Monitor, 104keys Keyboard
Processor: -                  Intel Pentium III processor.
Memory: -                    64 MB RAM, 20GB Hard Disk.
N/w Components: -      Network Adapter, RJ-45 Connector, UTP Cable, HUB.




















2.SOFTWARE: -

	This specifies the minimum requirement of  Software that is needed to install the System.

      The minimum requirements for Server.

       Operating System: -      MS-DOS, Windows 9x/XP (or) Windows NT.
  System Software : -        JDK 1.2.2 (or) JDK 1.3 (or) JDK 1.4.
       Application Software: -  Ftpser.class

The minimum requirements for Client.

       Operating System: -      MS-DOS, Windows 9x.
  Database: -                     Oracle.
  System Software : -        JDK 1.2.2 (or) JDK 1.3 (or) JDK 1.4.
       Application Software: - ActiveForm.class
     			    ChatForm.class	 
				    Sendall.class
				    Killall.class
				    Form.class
				    Filter.class
				    Chat.class














CHECKLIST TO INSTALL THE SOFTWARE IN THE CLIENT SYSTEMS

1. Check whether the Software folder ‘FTP’ is in the root directory ‘C:\THE COMPANY\FORMS6I ’.

2. Go to the folder FTP and double click the ‘SETUP.EXE’.

3. Setup automatically copies the files in the specified directories.

4.Check the 2 Icons ‘The Company Downloadings’ & ‘The Company Prompt’ is placed on the Desktop. If they were placed, then the installation process was successful.

5. Create the data source name ‘FTP’.
 (Note: start  settings  control panel  32 bit ODBC.) 






















CHECKLIST FOR DAILY RUNNING

Algorithmic Description of the process: -

1.	Click on the ‘The Company Downloadings’ Icon on the Desktop.
2.	The Main menu is activated. It contains the following options…
	Sending A Message
	Sending A File
3.	If the Option is ‘Sending A Message’.
4.	If the Server is presently running then you will be displayed with all the connected users information.
5.	To send a message to a specific client then click on that clients IP and give the message then click SEND..
6.	To send a message to all clients then type the message in the below Text field and
Then click SEND.

7.	If the Option is ‘Sending A File’.
8.	If the Server is presently running then you will be displayed with all the connected users information.
9.	To send a file to a specific client then click on that clients IP and give the Source path and Destination paths Correctly then click ‘SEND’.
10.	To send a file to a group of clients, click ‘SENDALL’, choose the client IPs, give the Source and destination paths, and then finally click ‘SEND’.
11.	To disconnect a client click ‘KILLALL’, choose the client IPs, and then finally click ‘KILL’.












CONCLUSION

I would like to conclude that the System has been launched 

successfully in the real environment, and is tested practically. 

The Files and Messages are transferred to the intended clients 

basing on the selection. Even .EXE files are also been 

transferred accurately with out any errors and perfectly 

executed after downloading.





























BIBILIOGRAPHY


1.	An Integrated Approach to Software Engineering
PANKAJ JALOTE.

2.	Java 2, Unleashed.
Jamie Jaworski.

3.	Java TM 2, The Complete Reference.
Patrick Naughton
Herbert Schildt.



















Sample Code for Ftpserver: -

import java.awt.*;
import java.awt.event.*;
import java.net.*;
import java.io.*;
import javax.swing.*;
import java.util.*;
import java.sql.*;
class Ftpser
{
public static void main(String ds[])
{
server3 s=new server3();
}
}
class server3 extends Thread
{
ServerSocket ser;
Socket cli;
static int no=0;
static Vector v1=new Vector(10);
static int port=143;
Vector v=new Vector(10);
static Vector donot=new Vector(10);
server3()
{
try
{
ser=new ServerSocket(port);
start();
//setDaemon(true);
}catch(Exception e){System.out.println(e);}
}





public void run()
{
while(true)
{
try
{
cli=ser.accept();
v.insertElementAt(new mul2(cli,this,no),no);
Runtime t=Runtime.getRuntime();
t.gc();
}catch(Exception e){System.out.println(e);}
}
}

void send(String msg)                           //noted
{
int flag=0;
for(int i=0;i<=no;i++)
{
flag=0;
for(int j=0;j<donot.size();j++)
{
int x=Integer.parseInt((String)donot.elementAt(j));
if(i==x)
flag=1;
}
if(flag==1)
continue;
mul2 m=(mul2)v.elementAt(i);
m.out1(msg);
}
}









void send1(String msg)
{
int flag1=0;
for(int i=0;i<no;i++)
{flag1=0;
for(int j=0;j<donot.size();j++)
{
int x=Integer.parseInt((String)donot.elementAt(j));
if(i==x)
flag1=1;
}
if(flag1==1)
continue;
mul2 m=(mul2)v.elementAt(i);
m.num=i;
m.out1(msg);
}
}
void send2(int no,String msg)
{
mul2 m=(mul2)v.elementAt(no);
m.out1(msg);
}

void sendall(int n,String msg)
{
for(int i=0;i<no;i++)
{
if(i==n)
continue;
mul2 m=(mul2)v.elementAt(i);
m.out1(msg);
}
}





void exit1(int n)
{
String s=v1.elementAt(n)+"  exited123";
v.removeElementAt(n);
v1.removeElementAt(n);
donot.removeElement(new String().valueOf(n));
Runtime t=Runtime.getRuntime();
t.gc();
no--;
send1(s);
}
}


class mul2 extends Thread
{
Socket client;
DataInputStream rin;
DataOutputStream out;
Statement stmt;
server3 ser;
String s;
String users;
byte b[]=new byte[200];
int num;
mul2(Socket cli,server3 ser,int num)
{
try
{
client=cli;
this.ser=ser;
this.num=num;
rin=new DataInputStream(cli.getInputStream());
out=new DataOutputStream(cli.getOutputStream());
start();
}catch(Exception e){System.out.println(e);}
}



public void run()
{
String msg="";
StringTokenizer str;
try
{
while(true)
{
byte b[]=new byte[200];
if(rin.read(b)>=1)
{
msg=new String(b).trim();
System.out.println("Hello");
System.out.println("Comming : "+msg);
if(msg.endsWith(" mustquit"))
{
str=new StringTokenizer(msg," ");
s=str.nextToken();
int in=server3.v1.indexOf(s);
System.out.println("The number is "+in);
ser.send2(in," mustquit");
} 
else
if(msg.indexOf("Theusername,")==0)
{
str=new StringTokenizer(msg," ");
str.nextToken();
String user=str.nextToken();
users="";
server3.v1.insertElementAt(user,server3.no);
System.out.println(" user "+user+" Connected... with no "+server3.no);
for(int i=0;i<=server3.no;i++)
users=users+server3.v1.elementAt(i)+" ";
ser.send(users+"allusers");
server3.no++;
}
else
if(msg.indexOf("transfering ")==0 || msg.indexOf("transfferingtoall ")==0)
{

str=new StringTokenizer(msg," ");
str.nextToken();
int size=Integer.parseInt(str.nextToken().trim());
String sender=str.nextToken().trim();

String all=str.nextToken("*");
String path=str.nextToken();
System.out.println("The size :"+size);
byte b1[]=new byte[size];
rin.readFully(b1,0,size);

System.out.println("came out");
StringTokenizer str1=new StringTokenizer(all," ");
System.out.println(path);
String mess=sender+" "+"sizel "+size+" "+path;
int i=1;
while(i<str1.countTokens())
{
int rec=server3.v1.indexOf(str1.nextToken().trim());
new sending(rec,b1,mess,ser);
}
}
else
if(msg.indexOf("nopath")>=0)
{
System.out.println("Entered in nopath");
str=new StringTokenizer(msg," ");
str.nextToken();
String rece=str.nextToken();
int x=server3.v1.indexOf(str.nextToken());
ser.send2(x,"nopath in "+rece);
}







Source Code for Activeclient

import java.awt.*;
import javax.swing.*;
import java.awt.event.*;
import java.net.*;
import java.io.*;
import java.util.*;
import java.sql.*;
public class chatform extends JFrame implements Runnable,ActionListener,MouseListener
{
JButton send,exit,kill;
JTextArea ta,ta1;
JTextField tf;
JLabel l1;
JScrollPane jsp,jsp1;
DataInputStream rin;
DataOutputStream out;
int n=0;
String user,mess;
JLabel l[]=new JLabel[100];
JPanel p2;
Vector v=new Vector();
Vector tip=new Vector();
//chat c1;
static int z=0;
byte b[]=new byte[50];
form f;
sendall all;
Connection con;
Statement stmt;
ResultSet rs,rs1,rs2;
static int in=0;
 public chatform(String user)
{
super("CONNECTED USERS INFORMATION");
this.user=user;
try{
Socket cli=new Socket("localhost",143);
rin=new DataInputStream(cli.getInputStream());
out=new DataOutputStream(cli.getOutputStream());
//InetAddress inet=InetAddress.getLocalHost();
//user=inet.getHostAddress();
byte x[]=("Theusername, "+user).getBytes();
System.out.println(new String(x));
out.write(x,0,x.length);
setSize(600,425);
setLocation(75,75);
show();
Container c=getContentPane();
JPanel p=new JPanel(new BorderLayout());
JPanel p1=new JPanel(new FlowLayout());
p2=new JPanel(new GridLayout(100,1,0,10));
ta=new JTextArea();
tf=new JTextField(50);
ta.setFont(new Font("",Font.BOLD,18));
ta.disable();
int v1=ScrollPaneConstants.VERTICAL_SCROLLBAR_ALWAYS;
int h=ScrollPaneConstants.HORIZONTAL_SCROLLBAR_ALWAYS;
jsp=new JScrollPane(ta,v1,h);
p.add(jsp,BorderLayout.CENTER);
p.add(tf,BorderLayout.SOUTH);
send=new JButton("SEND ALL");
exit=new JButton("EXIT");
kill=new JButton("KILL");
p1.add(kill);
p1.add(send);
p1.add(exit);
exit.addActionListener(this);
send.addActionListener(this);
kill.addActionListener(this);
l1=new JLabel("                        ALL CONNECTED USERS");
l1.setFont(new Font("helvatica",Font.BOLD,22));
l1.setForeground(Color.darkGray);
/*ta.addMouseListener(new MouseAdapter()
{
public void mouseEntered(MouseEvent me){
ta.disable();
}
public void mouseExited(MouseEvent me){
ta.enable();}
});*/
try
{
Class.forName("sun.jdbc.odbc.JdbcOdbcDriver");
con=DriverManager.getConnection("jdbc:odbc:raj");
stmt=con.createStatement();
rs=stmt.executeQuery("select *from users");
rs2=rs;
rs1=rs;
}
catch(Exception e){System.out.println(e);}
         rin.read(b);
         String str=new String(b).trim();
         System.out.println(str);
         StringTokenizer s=new StringTokenizer(str," ");
        while(s.hasMoreTokens())
        {
        String t=s.nextToken();
        rs1=stmt.executeQuery("select *from users");
        int flag=0,i=0;
        if(!t.equals("allusers"))
        {
        ta.append(t+"  :Presently Connected  "+"\n");
        v.addElement(t);
        while(rs1.next())
        {
        i++;
        if(t.trim().equals(rs1.getString(1)))
        {tip.addElement(rs1.getString(2));flag=1;}
        }
        if(flag==0)
        tip.addElement("Not Updated");
        System.out.println("sumitra"+i+" flag"+flag);
        }
        System.out.println(v.size()+" "+tip.size());
        }
        
for(int i=0;i<100;i++)
{
l[i]=new JLabel("");
p2.add(l[i]);
}
jsp1=new JScrollPane(p2,v1,h);

addlabel();


c.setLayout(new BorderLayout());
c.add(l1,BorderLayout.NORTH);
c.add(p1,BorderLayout.SOUTH);
c.add(jsp1,BorderLayout.EAST);
c.add(p,BorderLayout.CENTER);

show();
Thread t=new Thread(this);
t.start();
}catch(Exception e){System.out.println("anand1 "+e);}
}

public void actionPerformed(ActionEvent ae)
{
if(ae.getSource()==exit)
{
System.exit(0);
}
if(ae.getSource()==send)
{
Vector ve=new Vector(v);
in++;
all=new sendall(this,user,ve);
}
if(ae.getSource()==kill)
{
Vector ve=new Vector(v);
new killall(this,ve);
}
}
public void run()
{
String msg;
try
{
while(true)
{
byte b[]=new byte[200];
        if(rin.read(b)>=1)
        {
        msg=new String(b).trim();
//        System.out.println("Comming message :"+msg);
        if(msg.endsWith("allusers"))
        {
        StringTokenizer s=new StringTokenizer(msg," ");
        int x=s.countTokens();
        for(int i=1;i<x-1;i++)
        s.nextToken();
        String u=s.nextToken();
        ta.append(u+"  :Recently Connected"+"\n");
        v.addElement(u);
        rs2=stmt.executeQuery("select *from users");
        int flag=0;
        while(rs2.next())
        {
        if(u.trim().equals(rs2.getString(1)))
        {tip.addElement(rs2.getString(2));flag=1;}
        }
        if(flag==0)
        tip.addElement("Not Updated");
        System.out.println(v.size()+" "+tip.size());
        addlabel();
        }
        else
        if(msg.endsWith("exited123"))
        {
        System.out.println(msg);
        StringTokenizer s=new StringTokenizer(msg," ");
        String t=s.nextToken();
        ta.append(t+"  : Disconnected"+"\n");
        int x1=v.indexOf(t);
        v.removeElement(t);
        tip.removeElementAt(x1);
        System.out.println(v.size()+" "+tip.size());
        addlabel();
        }
        if(msg.indexOf("sizel")>=1)
        {
        int flag=0;
        System.out.println(msg);
        StringTokenizer str=new StringTokenizer(msg," ");
        String sender=str.nextToken();
        str.nextToken();
        int size=Integer.parseInt(str.nextToken());
        byte b1[]=new byte[size];
        try
        {
        String pat=str.nextToken();
        System.out.println("The dest Path "+pat);
        FileOutputStream fout=new FileOutputStream(pat);
        out.flush();
        rin.readFully(b1,0,size);
        fout.write(b1);
        System.out.println("File Captured");
        out.write(("captured "+" "+user+" "+sender).getBytes());
        //     System.out.println(new String(b1));
        }catch(Exception e){System.out.println(e);flag=1;}

        if(flag==1)
        {
        out.flush();
        out.write(("nopath "+" "+user+" "+sender).getBytes());
        }
        }
        if(msg.startsWith("captured"))
        {
        System.out.println("Entered in captured");
        System.out.println(msg);
        StringTokenizer str=new StringTokenizer(msg," ");
        str.nextToken();
        str.nextToken();
        String s=str.nextToken();
        //System.out.println(f.status2.getText());
        int ind=v.indexOf(s);
        l[ind].setForeground(Color.cyan);
        if(in==0)
        f.status2.append("File Transfered To System: "+s+"\n");
        else
        all.f.status2.append("File Transfered To System: "+s+"\n");
        }
        if(msg.startsWith("nopath"))
        {
        System.out.println("Entered in nopath");
        System.out.println(msg);
        StringTokenizer str=new StringTokenizer(msg," ");
        str.nextToken();
        str.nextToken();
        String s=str.nextToken();
        //System.out.println(f.status2.getText());
        if(in==0)
        f.status2.append("Path Not Found In System: "+s+"\n");
        else
        all.f.status2.append("Path Not Found In System: "+s+"\n");
        }
        if(msg.endsWith("mustquit"))
        {
        System.out.println("You have been Forcibly removed from server");
        System.exit(0);
        }
        }
}
}catch(Exception e){System.out.println("anand2 "+e);}
}
void addlabel()
{
System.out.println("The size is"+v.size());
for(int i=0;i<v.size();i++)
{
String t="   "+(String)v.elementAt(i)+"   ";
System.out.println(t);
l[i].setFont(new Font("",Font.BOLD,16));
l[i].setText(t);
l[i].setToolTipText((String)tip.elementAt(i));
if(user.equals((String)v.elementAt(i)))
{l[i].setForeground(Color.red);
continue;}
if(!l[i].getForeground().equals(Color.cyan))
l[i].setForeground(Color.blue);
l[i].addMouseListener(this);
}
for(int j=v.size();j<10;j++)
{l[j].setText("");l[j].removeMouseListener(this);l[j].setToolTipText("");}
}
public void mousePressed(MouseEvent me){}
public void mouseEntered(MouseEvent me){setCursor(Cursor.HAND_CURSOR);}
public void mouseExited(MouseEvent me){setCursor(Cursor.DEFAULT_CURSOR);}
public void mouseClicked(MouseEvent me){
if(me.getClickCount()==1)
{
JLabel l=(JLabel)me.getComponent();
in=0;
f=new form(this,l.getText(),user,null);
}

}
public void mouseReleased(MouseEvent me){}
public static void main(String ds[])
{
new chatform(ds[0]);
}
}










 



















INDEX

S.NO        CONTENTS	                                                    PAGE NO

01	       ABSTRACT 
02	        INTRODUCTION	
	        2.1.INTRODUCTION TO ORGANIZATION	
	        2.2.INTRODUCTION TO ENVIRONMENT	
	                2.2.1.SOFTWARE USED 
	                2.2.2.HARDWARE USED
03	        REQUIREMENT ANALYSIS	
	        3.1.PROBLEM ANALYSIS	
	              3.1.1.SCENARIOS & USE CASES	
	        3.2.FEASIBILITY STUDY	
	              3.2.1.TECHNICAL FEASIBILITY	
	              3.2.2.OPERATIONAL FEASIBILITY	
	              3.2.3.ECONOMIC FEASIBILITY	
	                     3.2.3.1.COST-BENEFIT ANALYSIS	
         	        3.3.PREPARATION OF REQUIREMENT     
                         SPECIFICATION                 	
	               3.3.1.SOFTWARE REQUIREMENT  
                                  SPECIFICATION 
04	SOFTWARE DESIGN	
	4.1.OBJECT ORIENTED DESIGN METHODOLOGY	
	    4.1.1.INTRODUCTION	
	    4.1.2.DESIGN TOOLS UTILISED	
	          4.1.2.1.ACTIVITY DIAGRAMS	
	          4.1.2.2.SEQUENCE DIAGRAMS	
	          4.1.2.3.CLASS DIAGRAMS	
	          4.1.2.4.OBJECT DIAGRAMS	
	          4.1.2.5.STATE TRANSITION DIAGRAMS	

05	DATABASE DESIGN	
	5.1.INTRODUCTION 	
	5.2.E-R DIAGRAMS	
	5.3.NORMAL FORMS IMPLEMENTED	
	5.4.TABLE DESCRIPTIONS	

S.NO        CONTENTS	                                                     PAGE NO

06	    TESTING	
	    6.1.STRUCTURAL TESTING (WHITE BOX)	
	          6.1.1.INTRODUCTION	
	          6.1.2.LIST OF TEST CASES PREPARED	
	    6.2.FUNCTIONAL TESTING (BLACK BOX)	
	          6.2.1.INTRODUCTION	
	          6.2.2.LIST OF TEST CASES PREPARED	

07	    FORMS DESIGN	
	    7.1.INPUT FORMS DESIGN 
	    7.2.OUTPUT FORMS DESIGN 

08	    IMPLEMENTATION/USER INTERFACE	
	    8.1.ALGORITHMIC / NAVIGATIONAL DESCRIPTION	                    

09	    CONCLUSION	

10  	    BIBILIOGRAPHY	

11	    APPENDIX	
	    11.1.ANNEXURE-I (SCREEN LAYOUTS)	
	    11.2.ANNEXURE-II  (SAMPLE CODE)	
	    11.3.ANNEXURE-IV (GLOSSARY:  ABBREVATION & 
                      ACRONYMS)	



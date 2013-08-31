ganib
=====

Project Management Software (Open Source, tasks, bug tracking, agile scrum, timesheet, wiki)

Ganib v1.0 Software License
 * 					 
 * Ganib | Online web based project planning, collaboration and management software.					 
 * Copyright (c) 2011-2013 Ganib Enterprises. All rights reserved. 
 * 
 * Use this license to use or redistribute the Ganib software v1.0+ and later versions. 
 * 

 * For free support for Ganib users, questions should be posted to the community of 
 * Ganib users at help.ganib.com.

CONTENTS

1) FEATURES
2) REQUIREMENTS
3) INSTALLATION

=======================================================
FEATURES
=======================================================

-- Import Export MSP
	100% Compatible with Microsoft Project format (XML)
-- Timesheet
	Easy to use Timesheet with Monthly, Weekly & Assignments view
-- Plan and Manage
	Feature rich Workplan with single page management
-- Collaboration
	Collabroate with team using Blogs, Wiki & Discussions
-- Lists
	Forms & Filters
-- Themes
	Themes which can be set as per the users liking


=========================================================
REQUIREMENTS
=========================================================

-- Apache tomcat6/7
-- JAVA 6
-- MySQL-5.0 & above

==========================================================
	INSTALLATION
==========================================================

1) Make sure that MySQl & Apache Tomcat is installed on system.

2) Move war file to tomcat webappas directory.
   -- mv ganib.war TOMCAT_HOME/webapps/

3) Now edit TOMCAT_HOME/bin/context.xml file to change database connection properties.
      < Resource name="jdbc/GanibDB"
             auth="Container"
             type="javax.sql.DataSource"
             username="root" password=""
             driverClassName="com.mysql.jdbc.Driver"
             url="jdbc:mysql://localhost:3306/ganib?autoReconnect=true&useUnicode=true&characterEncoding=utf-8""
             maxActive="125"
         maxIdle="25"
     />

4) Replace username, password & database name from url.

5) To change SMTP settings you need to edit TOMCAT_HOME/conf/context.xml & edit below lines.

< Resource
     name="mail/GanibSession"
     type="javax.mail.Session"
     auth="Container"
     mail.smtp.host="localhost" 
     mail.smtp.auth="false" 
     username="username"
     password="password" 
     mail.user="username"
     mail.password="password"
     mail.smtp.port="25"
     mail.transport.protocol="smtp"
     mail.debug="true"
/>


6) Bydefault ganib run on port 8080. If port 8080 is already in use, you can change port by editing tomcat_home/conf/server.xml.
< Connector port="7070" protocol="HTTP/1.1" 
               connectionTimeout="20000" 
                URIEncoding="UTF-8"
               redirectPort="8443"
/>
7) Change connector port from above lines to run ganib on another port.

=========================================================
MySQL Database
=========================================================
Now you need to import database script files.
    MySQL -u root -p
     mysql > CREATE DATABASE db_name CHARACTER SET utf8 COLLATE utf8_general_ci;
     mysql > exit;
     mysql -h host -u root -p ganib < PATH_TO_ganib_dir/database/ganib.sql

========================================================

8) Now you need to start ganib with below commands.
    -- tomcat_home/bin/startup.sh --or-- service ganib start 

9) If everything is configured as per above instructions. you can access it using web browser. Enter below url in web browser.

http://localhost:8080/ganib/ 

Replace "localhost" with your system IP address. Also you need to replace port no if you've changed it.

That's it !!!!!

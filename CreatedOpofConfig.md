# after kubectl create cm usermanagement --from-file=dump_mysql.sql,this is how cm is op

apiVersion: v1
data:
  data_backup.sql : "-- MySQL dump 10.13  Distrib 5.7.18, for Linux (x86_64)\n--\n-- Host:
    localhost    Database: accounts\n-- ------------------------------------------------------\n--
    Server version\t5.7.18-0ubuntu0.16.10.1\n\n/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT
    */;\n/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;\n/*!40101
    SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;\n/*!40101 SET NAMES utf8
    */;\n/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;\n/*!40103 SET TIME_ZONE='+00:00'
    */;\n/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;\n/*!40014
    SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;\n/*!40101
    SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;\n/*!40111 SET
    @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;\n\n--\n-- Table structure for table
    `role`\n--\n\nDROP TABLE IF EXISTS `role`;\n/*!40101 SET @saved_cs_client     =
    @@character_set_client */;\n/*!40101 SET character_set_client = utf8 */;\nCREATE
    TABLE `role` (\n  `id` int(11) NOT NULL AUTO_INCREMENT,\n  `name` varchar(45)
    DEFAULT NULL,\n  PRIMARY KEY (`id`)\n) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT
    CHARSET=utf8;\n/*!40101 SET character_set_client = @saved_cs_client */;\n\n--\n--
    Dumping data for table `role`\n--\n\nLOCK TABLES `role` WRITE;\n/*!40000 ALTER
    TABLE `role` DISABLE KEYS */;\nINSERT INTO `role` VALUES (1,'ROLE_USER');\n/*!40000
    ALTER TABLE `role` ENABLE KEYS */;\nUNLOCK TABLES;\n\n--\n-- Table structure for
    table `user`\n--\n\nDROP TABLE IF EXISTS `user`;\n/*!40101 SET @saved_cs_client
    \    = @@character_set_client */;\n/*!40101 SET character_set_client = utf8 */;\nCREATE
    TABLE `user` (\n  `id` int(11) NOT NULL AUTO_INCREMENT,\n  `username` varchar(255)
    DEFAULT NULL,\n  `userEmail` varchar(255) DEFAULT NULL,\n  `profileImg` varchar(255)
    DEFAULT NULL,\n  `profileImgPath` varchar(255) DEFAULT NULL,\n  `dateOfBirth`
    varchar(255) DEFAULT NULL,\n  `fatherName` varchar(255) DEFAULT NULL,\n  `motherName`
    varchar(255) DEFAULT NULL,\n  `gender` varchar(255) DEFAULT NULL,\n  `maritalStatus`
    varchar(255) DEFAULT NULL,\n  `permanentAddress` varchar(255) DEFAULT NULL,\n
    \ `tempAddress` varchar(255) DEFAULT NULL,\n  `primaryOccupation` varchar(255)
    DEFAULT NULL,\n  `secondaryOccupation` varchar(255) DEFAULT NULL,\n  `skills`
    varchar(255) DEFAULT NULL,\n  `phoneNumber` varchar(255) DEFAULT NULL,\n  `secondaryPhoneNumber`
    varchar(255) DEFAULT NULL,\n  `nationality` varchar(255) DEFAULT NULL,\n  `language`
    varchar(255) DEFAULT NULL,\n  `workingExperience` varchar(255) DEFAULT NULL,\n
    \ `password` varchar(255) DEFAULT NULL,\n  PRIMARY KEY (`id`)\n) ENGINE=InnoDB
    AUTO_INCREMENT=14 DEFAULT CHARSET=utf8;\n/*!40101 SET character_set_client = @saved_cs_client
    */;\n\n--\n-- Dumping data for table `user`\n--\n\nLOCK TABLES `user` WRITE;\n/*!40000
    ALTER TABLE `user` DISABLE KEYS */;\nINSERT INTO `user` VALUES (7,'admin_vp','admin@visualpathit.com',NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,'$2a$11$0a7VdTr4rfCQqtsvpng6GuJnzUmQ7gZiHXgzGPgm5hkRa3avXgBLK'),(8,'WahidKhan','wahid.khan74@gmail.com',NULL,NULL,'28/03/1994','M
    Khan','R Khan','male','unMarried','Ameerpet,Hyderabad','Ameerpet,Hyderabad','Software
    Engineer','Software Engineer','Java HTML CSS ','8888888888','8888888888','Indian','english','2
    ','$2a$11$UgG9TkHcgl02LxlqxRHYhOf7Xv4CxFmFEgS0FpUdk42OeslI.6JAW'),(9,'Gayatri','gayatri@gmail.com',NULL,NULL,'20/06/1993','K','L','male','unMarried','Ameerpet,Hyderabad','Ameerpet,Hyderabad','Software
    Engineer','Software Engineer','Java HTML CSS ','9999999999','9999999999','India','english','5','$2a$11$gwvsvUrFU.YirMM1Yb7NweFudLUM91AzH5BDFnhkNzfzpjG.FplYO'),(10,'WahidKhan2','wahid.khan741@gmail.com',NULL,NULL,'28/03/1994','M
    Khan','R Khan','male','unMarried','Ameerpet,Hyderabad','Ameerpet,Hyderabad','Software
    Engineer','Software Engineer','Java HTML CSS ','7777777777','777777777','India','english','7','$2a$11$6oZEgfGGQAH23EaXLVZ2WOSKxcEJFnBSw2N2aghab0s2kcxSQwjhC'),(11,'KiranKumar','kiran@gmail.com',NULL,NULL,'8/12/1993','K
    K','RK','male','unMarried','California','James Street','Software Engineer','Software
    Engineer','Java HTML CSS ','1010101010','1010101010','India','english','10','$2a$11$EXwpna1MlFFlKW5ut1iVi.AoeIulkPPmcOHFO8pOoQt1IYU9COU0m'),(12,'Saikumar','sai@gmail.com',NULL,NULL,'20/06/1993','Sai
    RK','Sai AK','male','unMarried','California','US','Software Engineer','Software
    Engineer','Java HTML CSS AWS','8888888111','8888888111','India','english','8','$2a$11$pzWNzzR.HUkHzz2zhAgqOeCl0WaTgY33NxxJ7n0l.rnEqjB9JO7vy'),(13,'RamSai','ram@gmail.com',NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,'$2a$11$6BSmYPrT8I8b9yHmx.uTRu/QxnQM2vhZYQa8mR33aReWA4WFihyGK');\n/*!40000
    ALTER TABLE `user` ENABLE KEYS */;\nUNLOCK TABLES;\n\n--\n-- Table structure for
    table `user_role`\n--\n\nDROP TABLE IF EXISTS `user_role`;\n/*!40101 SET @saved_cs_client
    \    = @@character_set_client */;\n/*!40101 SET character_set_client = utf8 */;\nCREATE
    TABLE `user_role` (\n  `user_id` int(11) NOT NULL,\n  `role_id` int(11) NOT NULL,\n
    \ PRIMARY KEY (`user_id`,`role_id`),\n  KEY `fk_user_role_roleid_idx` (`role_id`),\n
    \ CONSTRAINT `fk_user_role_roleid` FOREIGN KEY (`role_id`) REFERENCES `role` (`id`)
    ON DELETE CASCADE ON UPDATE CASCADE,\n  CONSTRAINT `fk_user_role_userid` FOREIGN
    KEY (`user_id`) REFERENCES `user` (`id`) ON DELETE CASCADE ON UPDATE CASCADE\n)
    ENGINE=InnoDB DEFAULT CHARSET=utf8;\n/*!40101 SET character_set_client = @saved_cs_client
    */;\n\n--\n-- Dumping data for table `user_role`\n--\n\nLOCK TABLES `user_role`
    WRITE;\n/*!40000 ALTER TABLE `user_role` DISABLE KEYS */;\nINSERT INTO `user_role`
    VALUES (4,1),(5,1),(6,1),(7,1),(8,1),(9,1),(10,1),(11,1),(12,1),(13,1);\n/*!40000
    ALTER TABLE `user_role` ENABLE KEYS */;\nUNLOCK TABLES;\n/*!40103 SET TIME_ZONE=@OLD_TIME_ZONE
    */;\n\n/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;\n/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS
    */;\n/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;\n/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT
    */;\n/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;\n/*!40101
    SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;\n/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES
    */;\n\n-- Dump completed on 2017-12-07 16:32:31\n"
kind: ConfigMap
metadata:
  creationTimestamp: "2021-06-25T07:01:56Z"
  name: usermanagement
  namespace: default
  resourceVersion: "37763"
  uid: 4c259a10-9637-4058-81d9-af013a90543e



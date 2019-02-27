
Description:

This project is designed to test 4 simple HTTP methods : GET , POST , PUT and DELETE using the Orchestrator instance that is available. In order to achieve this it follows the folowing sequence:

1. Obtain from orchestrator the data needed for connecting (OrchestratorURL, OrchestratorTennant, OrchestratorUser, OrchestratorUserPassword)
2. Obtain an authenticaton token from orchestrator -- aka login in Orchestrator 
3. Create a robot ( make a POST call to  odata/Robots with the details of the robot to be created , if the call was successfull the robot's name and id are added the "CreatedRobotsQueue" queue)
4. Search for the newly created robot ( consume from "CreatedRobotsQueue" , and search for the robot. if successfull add the robot's details to the "toBeEditedRobotsQueue" queue)
5. Update a robot (consume from "toBeEditedRobotsQueue" , and update the  robot. if successfull add the robot's details to the "toBeDeletedRobotsQueue" queue )
6. Delete robot ( consume from "toBeDeletedRobotsQueue" and delete the robots )


Prerequisites:

Prior to running the SimpleRobotAPI project the following must be created and configured in Orchestrator

1. Orchestrator assests
Name: OrchestratorURL Example: https://roqanlb02.qa.test Description: The URL of the Orchestrator instance that will run the workflow
Name: OrchestratorTennant Example: Staging Description: The tennant that will be used for the test
Name: OrchestratorUser Example: DragosSuma Description: The user that will be used to connect to the Orchestrator instance and create, update , delete the robots.
Name: OrchestratorUserPassword Example: ****** Description: The password of the previously mentioned user
Name: DBConnString Example: Data Source=qa-sqlcluster01.qa.test;Initial Catalog=UiPath_184ON;User ID=sa;Password=1qazXSW@ Description: The DB connection string to the DB that is used by the Orchestrator Instance


2. Orchestrator QUEUEs

Name: CreatedRobotsQueue 
Name: toBeDeletedRobotsQueue
Name: toBeEditedRobotsQueue

Note: All queues must be created using "Unique Reference" set to true.




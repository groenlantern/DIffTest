run:
null to tom - tom is friends with dick that is friends with tom 
1 Create:Person
1.1	 Create:firstName as "Tom"
1.2	 Create:surname as "SurnameTom"
1.3	 Create:friend
1.3		 Create:Person
1.3.1			 Create:firstName as "Dick"
1.3.2			 Create:surname as "Dickson"
1.3.3			 Create:nickNames as "{"Dicky","Richard","Rich","Dickson"}"
1.4	 Create:nickNames as "{"Thomas","Tomee","Tomson"}"

Apply Diff to null - Should Become Tom

New Tom Object
FistName is Tom
SurName is SurnameTom
NickNames is ["Tomee", "Thomas", "Tomson"]
Friend Obj is Dick
	FistName is Dick
	SurName is Dickson
	NickNames is ["Richard", "Dickson", "Dicky", "Rich"]
	Friend Obj is Tom

Harry to Harry
No Differences Found

Dick to Harry
1 Update:Person
1.1	 Update:firstName from "Dick" to "Harry"
1.2	 Update:surname from "Dickson" to "Potter"
1.3	 Update:friend
1.3		 Update:Person
1.3.1			 Update:firstName from "Tom" to "Susan"
1.3.2			 Update:surname from "SurnameTom" to "Cooper"
1.3.3			 Update:friend
1.3.3				 Update:Person
1.3.3.1					 Update:firstName from "Dick" to "June"
1.3.3.2					 Update:surname from "Dickson" to "Joyce"
1.3.3.3					 Delete:friend
1.3.3.4					 Update:nickNames from "{"Dicky","Richard","Rich","Dickson"}" to "{"Pearl","July","February"}"
1.3.4			 Delete:nickNames
1.4	 Update:nickNames from "{"Dicky","Richard","Rich","Dickson"}" to "{"TheNameToBeSpoken","Potter"}"

null to Susan
1 Create:Person
1.1	 Create:firstName as "Susan"
1.2	 Create:surname as "Cooper"
1.3	 Create:friend
1.3		 Create:Person
1.3.1			 Create:firstName as "June"
1.3.2			 Create:surname as "Joyce"
1.3.3			 Create:nickNames as "{"Pearl","July","February"}"

Carrol to Null
1 Delete:Person

Susan to June
1 Update:Person
1.1	 Update:firstName from "Susan" to "June"
1.2	 Update:surname from "Cooper" to "Joyce"
1.3	 Delete:friend
1.4	 Create:nickNames as "{"Pearl","July","February"}"

June to Susan
1 Update:Person
1.1	 Update:firstName from "June" to "Susan"
1.2	 Update:surname from "Joyce" to "Cooper"
1.3	 Update:friend
1.3		 Create:Person
1.3.1			 Create:firstName as "June"
1.3.2			 Create:surname as "Joyce"
1.3.3			 Create:nickNames as "{"Pearl","July","February"}"
1.4	 Delete:nickNames

BUILD SUCCESSFUL (total time: 0 seconds)

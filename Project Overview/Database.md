### USERS collection
1) name
2) email
3) mobile
4) password
5) role
6) profile_img
7) userId
8) firebase_id
9) family_id

#### Format
user_data  = {
"name" : "",     
"email" : "",
"mobile" : "",
"password" : "",
"role" : "",
"profile_img" : ""
}


### INFO collection
1) userId
2) name
3) relation
4) tagline
5) triggermemory

#### Format
info_data = {
"userId" : "",
"relation" : "",
"tagline" : "",
"triggermemory" : ""
}

### REMINDERS collection
1) title
2) description
3) date
4) status
5) userId
6) remId
7) important
8) urgent

#### Format

reminders_data = {
"title" : "",
"description" : "",
"date" : "",
"status" : "",
"userId" ; "",
"important" : "",
"urgent" : ""
}

### FAMILIES collection
1) family_id
2) created_by
3) members
4) patient

### LOCATION collection
1) userId
2) home_location: 
	1) latitude
	2) longitude
3) curr_location: 
	1) latitude
	2) longitude


# claimIt
A blockchain solution for car accident insurance claim based on hyperledger fabric

Description
1.	An insuree reports an accident (<=7 days)
2.	A broker, agent or insurance company provides requested information
3.	A broker submits a claim to an issuer
4.	An issuer approves or rejects the claim
5. The claim is resolved


Car Accident Insurance Claim modeling
A. State Data
States: [“No accident”, “Claim Started”, “Claim Awaiting Submission”, “Claim Approved”, “Resolve Claim”]

State: 0

Insuree: {
Name: ‘’”,
Policy Number: “”,
Address: “”,
Insurer: “”
}

Car Details: {
Car Make: “”
Car Model: “”
Car Year: “”,
Registration: “”,
License No.: “”
}

Driver: {
Driver Name: “”,
License No.: “”
}

Passenger: [
Name: “”
]
Accident Details: {
Driver Name: ‘’,
License No.: “”
Date: “”,
Time: “”,
Location: “”,
Description: “”
}


B. Transitions
•	ReportAccident (Name, Address)
•	ProvideInformation (Insuree, Car, Driver, Passenger, Accident Details)
•	Incomplete(Name)
•	SubmitClaim (Insuree, Amount Covered)
•	Approve(Name, Amount)
•	Reject(Name)

C. Functions
•	CheckStatus (Name)
•	CheckRule (Name, Date, Location)
•	ContestDecision(Name, Date, Location, Case)

D. Roles
•	ReportAccident - Insuree
•	ProvideInformation - Insuree
•	SubmitClaim - Broker
•	ApproveClaim – Insurer
•	CheckStatus - Insuree, Insurer, Broker
•	CheckRule – Insuree, Broker
•	ContetstDecision - Insuree


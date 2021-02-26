# claimIt

A blockchain solution for car accident insurance claim based on
hyperledger fabric. <br>

Description 
1. An insuree reports an accident (<=7 days) <br>
2. A broker, agent or insurance company provides requested information <br>
3. A broker submits a claim to an issuer <br>
4. An issuer approves or rejects the claim <br>
5. The claim is resolved <br>


![alt text](state_diag_claimIt.png?raw=true) <br>

Car Accident Insurance Claim modeling <br>
<em> A.  State Data </em> <br>
States: [“No accident”, “Claim Started”, “Claim Awaiting Submission”, “Claim Approved”, “Resolve Claim”] <br>

State: 0 <br>

Insuree: { Name: ‘’”, Policy Number: “”, Address: “”, Insurer: “” } <br>

Car Details: { Car Make: “” Car Model: “” Car Year: “”, Registration:
“”, License No.: “” } <br>

Driver: { Driver Name: “”, License No.: “” } <br>

Passenger: [Name: “”] Accident Details: { Driver Name: ‘’, License No.:
“” Date: “”, Time: “”, Location: “”, Description: “” } <br>

<em> B. Transitions </em>
<ol>
    <li> ReportAccident (Name, Address) </li>
    <li> ProvideInformation (Insuree, Car, Driver, Passenger, Accident Details) </li>
    <li> Incomplete(Name) </li>
    <li> SubmitClaim (Insuree, Amount Covered) </li>
    <li> Approve(Name, Amount) </li>
    <li> Reject(Name) </li>
</ol>

<em> C. Functions </em>
<ul>
    <li> CheckStatus (Name) </li>
    <li> CheckRule (Name, Date, Location) </li>
    <li> ContestDecision(Name, Date, Location, Case) </li>
</ul>


<em> D. Roles </em>
<ul> 
    <li> ReportAccident - Insuree  </li>
    <li> ProvideInformation - Insuree  </li>
    <li> SubmitClaim - Broker </li>
    <li> ApproveClaim – Insurer </li>
    <li> CheckStatus - Insuree, Insurer, Broker </li>
    <li> CheckRule – Insuree, Broker </li>
    <li> ContetstDecision - Insuree </li>
</ul>


# claimIt

A blockchain solution for car accident insurance claim based on
hyperledger fabric. <br>

<h3> Description </h3>
1. An insuree reports an accident (<=7 days) <br>
2. A broker, agent or insurance company provides requested information <br>
3. A broker submits a claim to an issuer <br>
4. An issuer approves or rejects the claim <br>
5. The claim is resolved <br>


![alt text](state_diag_claimIt.png?raw=true) <br>

<h3>Car Accident Insurance Claim modeling </h3>
<h4> A.  State Data </h4>
States: <strong> [“No accident”, “Claim Started”, “Claim Awaiting Submission”, “Claim Approved”, “Resolve Claim”]</strong><br>

State: 0 <br>

Insuree: { Name: ‘’”, Policy Number: “”, Address: “”, Insurer: “” } <br>

Car Details: { Car Make: “”, Car Model: “”, Car Year: “”, Registration: “”, License No.: “” } <br>

Driver: { Driver Name: “”, License No.: “” } <br>

Passengers: ["Passenger Name", ] <br>

Accident Details: { Driver Name: "", License No.:“”, Date: “”, Time: “”, Location: “”, Description: “” } <br>

<h4> B. Transitions </h4>
<ol>
    <li> ReportAccident (Name, Address) </li>
    <li> ProvideInformation (Insuree, Car, Driver, Passenger, Accident Details) </li>
    <li> Incomplete (Name) </li>
    <li> SubmitClaim (Insuree, Amount Covered) </li>
    <li> Approve (Name, Amount) </li>
    <li> Reject (Name) </li>
</ol>

<h4> C. Functions </h4>
<ul>
    <li> CheckStatus (Name) </li>
    <li> CheckRule (Name, Date, Location) </li>
    <li> ContestDecision(Name, Date, Location, Case) </li>
</ul>


<h4> D. Roles </h4>
<ul> 
    <li> ReportAccident - Insuree  </li>
    <li> ProvideInformation - Insuree  </li>
    <li> SubmitClaim - Broker </li>
    <li> ApproveClaim – Insurer </li>
    <li> CheckStatus - Insuree, Insurer, Broker </li>
    <li> CheckRule – Insuree, Broker </li>
    <li> ContetstDecision - Insuree </li>
</ul>


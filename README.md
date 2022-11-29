<!DOCTYPE html>
<html>
<head>
    <title>License Fees Calculator</title>
</head>
<style>
    select.license{
        padding:10px;
        color:red;
        margin:100px;
        align:center;
        width:30%;
        border:5px;
    }

    select.class{
        padding:10px;
        color:blue;
        margin:100px;
        align:center;
        border:5px;
        width:30%;
    }
    .selectDiv{
        background-color:#0cd1ad;
        width:100%;
        height:450px;
    }
    .tileDiv{
        text-align:center;
        margin:0 20px;
        padding:10px;
        font-weight:bold;
        font-size:28px;
    }
</style>
<body>
<div class="tileDiv">License Fees Calculator</div>
<div class="selectDiv">
    <select class="license" id="license" onchange="updateClass();">License</select>
    <select class="class" id="class" onchange="updateFees();">Class</select>
    <select class="class" type="number" id="fees" >Total Fees</select>
    <select class="class" type="number" id="renewalFees"hidden>Renewal Fees</select> <!-- ID For Renewal Fees -->
    <select class="class" type="number" id="reFees"  hidden>Renewal Fees</select>    <!-- ID For Renewal years -->
    <select class="class" type="number" id="lateFees"  hidden>Late Fees</select>    <!-- ID For Renewal years -->

    <label for="">License Expiry Date</label>
    <input type="date" onchange="lateFees()" id="exDate">

    <label for="">Renewal Years</label> <!-- This is a comment -->
    <input type="number" id="reYears"  name="reYears" min="1" max="5"> <!-- This is a comment onchange="updateYears()"-->

    <label for="">Renewal Date</label>
    <input type="date" id="reDate" onchange="updateYears()">

    <button onclick="calculateDays()">Your Fees</button>
    <p id="output"></p>

<!--    <label for="">Total Fees</label>-->
    <p id="totalFees" type="number"></p>


</div>
<script>
    var myArrayLicenseType = [
        {
            "License" : "Select License Type"
        },
        {
            "License" : "Contractor"
        },
        {
            "License" : "Supervisor"
        },
        {
            "License" : "Electrician"
        }
    ];

    function lateFees() {
        var zone = document.getElementById("license");

        if (zone.value == "Contractor"){
            // alert("You clicked ABC Class.");

            var myArrayFees = [
                {
                    "lateFees" : 300
                }
            ];
        }
        else if (zone.value == "Supervisor"){
            // alert("You clicked BC Class.");
            var myArrayFees = [
                {
                    "lateFees" : 90
                }
            ];
        }
        else if (zone.value == "Electrician"){
            // alert("You clicked BC Class.");
            var myArrayFees = [
                {
                    "lateFees" : 30
                }
            ];
        }

        calculateLateFees(myArrayFees)
    }

    function updateYears() {

        var zone = document.getElementById("license");
        var fees = document.getElementById("class");

        if (fees.value == "ABC Class" && zone.value == "Contractor"){
            // alert("You clicked ABC Class.");

            var myArrayFees = [
                {
                    "feesRenew" : 4200
                }
            ];
        }
        else if (fees.value == "BC Class" && zone.value == "Contractor"){
            // alert("You clicked BC Class.");
            var myArrayFees = [
                {
                    "feesRenew" : 1800
                }
            ];
        }
        else if (fees.value == "C Class" && zone.value == "Contractor")
        {
            // alert("You clicked C Class");
            var myArrayFees = [
                {
                    "feesRenew" : 600
                }
            ];
        }
        else if (fees.value == "ABC Class" && zone.value == "Supervisor")
        {
            // alert("You clicked ABC Class");
            var myArrayFees = [
                {
                    "feesRenew" : 1320
                }
            ];
        }
        else if (fees.value == "BC Class" && zone.value == "Supervisor")
        {
            // alert("You clicked BC Class");
            var myArrayFees = [
                {
                    "feesRenew" : 720
                }
            ];
        }
        else if (fees.value == "C Class" && zone.value == "Supervisor")
        {
            // alert("You clicked C Class");
            var myArrayFees = [
                {
                    "feesRenew" : 300
                }
            ];
        }
        else if (fees.value == "ABC Class" && zone.value == "Electrician")
        {
            // alert("You clicked ABC Class");
            var myArrayFees = [
                {
                    "feesRenew" : 180
                }
            ];
        }
        else if (fees.value == "BC Class" && zone.value == "Electrician")
        {
            // alert("You clicked BC Class");
            var myArrayFees = [
                {
                    "feesRenew" : 90
                }
            ];
        }
        else if (fees.value == "C Class" && zone.value == "Electrician")
        {
            // alert("You clicked C Class");
            var myArrayFees = [
                {
                    "feesRenew" : 30
                }
            ];
        }

        calculateRenewalFees(myArrayFees)
    }


    function updateFees() {
        var fees = document.getElementById("class");
        var zone = document.getElementById("license");

        if (fees.value == "ABC Class" && zone.value == "Contractor"){
            alert("You clicked ABC Class.");

            var myArrayFees = [
                {
                    "fees" : "8400"
                }
            ];
        }
        else if (fees.value == "BC Class" && zone.value == "Contractor"){
            alert("You clicked BC Class.");
            var myArrayFees = [
                {
                    "fees" : 3600
                }
            ];
        }
        else if (fees.value == "C Class" && zone.value == "Contractor")
        {
            alert("You clicked C Class");
            var myArrayFees = [
                {
                    "fees" : "1200"
                }
            ];
        }
        else if (fees.value == "ABC Class" && zone.value == "Supervisor")
        {
            alert("You clicked ABC Class");
            var myArrayFees = [
                {
                    "fees" : "3600"
                }
            ];
        }
        else if (fees.value == "BC Class" && zone.value == "Supervisor")
        {
            alert("You clicked BC Class");
            var myArrayFees = [
                {
                    "fees" : "1800"
                }
            ];
        }
        else if (fees.value == "C Class" && zone.value == "Supervisor")
        {
            alert("You clicked C Class");
            var myArrayFees = [
                {
                    "fees" : "600"
                }
            ];
        }
        else if (fees.value == "ABC Class" && zone.value == "Electrician")
        {
            alert("You clicked ABC Class");
            var myArrayFees = [
                {
                    "fees" : "300"
                }
            ];
        }
        else if (fees.value == "BC Class" && zone.value == "Electrician")
        {
            alert("You clicked BC Class");
            var myArrayFees = [
                {
                    "fees" : "240"
                }
            ];
        }
        else if (fees.value == "C Class" && zone.value == "Electrician")
        {
            alert("You clicked C Class");
            var myArrayFees = [
                {
                    "fees" : "90"
                }
            ];
        }

        feesFunction(myArrayFees)
    }


    function updateClass() {
        var zone = document.getElementById("license");

        if (zone.value == "Contractor"){

            alert("You clicked Contractor.");
            var myArrayClass = [
                {
                    "class" : "Select Class Type"
                },
                {
                    "class" : "ABC Class"
                },
                {
                    "class" : "BC Class"
                },
                {
                    "class" : "C Class"
                }
            ];
            classFunction(myArrayClass);
        }

        if (zone.value == "Supervisor"){

            alert("You clicked Supervisor");
            var myArrayClass = [
                {
                    "class" : "ABC Class"
                },
                {
                    "class" : "BC Class"
                },
                {
                    "class" : "C Class"
                }
            ];
            classFunction(myArrayClass);
        }

        if (zone.value == "Electrician"){

            alert("You clicked Electrician.");
            var myArrayClass = [
                {
                    "class" : "ABC Class"
                },
                {
                    "class" : "BC Class"
                },
                {
                    "class" : "C Class"
                }
            ];
            classFunction(myArrayClass);
        }
    }

    function calculateLateFees(arr) {
        var out = "";
        var i;

        for(i = 0; i < arr.length; i++) {
            out += '<option value="' + arr[i].lateFees + '">' + arr[i].lateFees + '</option>' +
                arr[i].display + '</a><br>';
        }
        document.getElementById("lateFees").innerHTML = out;

    }

    // calculateRenewalFees(myArrayFees1);

    function calculateRenewalFees(arr) {
        var out = "";
        var i;

        for(i = 0; i < arr.length; i++) {
            out += '<option value="' + arr[i].feesRenew + '">' + arr[i].feesRenew + '</option>' +
                arr[i].display + '</a><br>';
        }
        document.getElementById("renewalFees").innerHTML = out;
    }

    LicenseFunctionType(myArrayLicenseType);
    function LicenseFunctionType(arr) {
        var out = 0;
        var i;

        for(i = 0; i < arr.length; i++) {
            out += '<option value="' + arr[i].License + '">' + arr[i].License + '</option>' +
                arr[i].display + '</a><br>';
        }

        document.getElementById("license").innerHTML = out;
    }

    function classFunction(arr) {
        var out = "";
        var i;

        for(i = 0; i < arr.length; i++) {
            out += '<option value="' + arr[i].class + '">' + arr[i].class + '</option>' +
                arr[i].display + '</a><br>';
        }
        document.getElementById("class").innerHTML = out;
    }

    // feesFunction(myArrayFees);
    function feesFunction(arr) {
        var out = 0;
        var i;

        for(i = 0; i < arr.length; i++) {
            out += '<option value="' + arr[i].fees + '">' + arr[i].fees + '</option>' +
                arr[i].display + '</a><br>';
        }

        document.getElementById("fees").innerHTML = out;
    }

            //    Date Section
    function calculateDays() {

        var fees1 = document.getElementById("fees").value;

        alert(fees1);

        var d1 = document.getElementById("exDate").value;
        var d2 = document.getElementById("reDate").value;
        var d3 = document.getElementById("renewalFees").value;
        var d4 = document.getElementById("lateFees").value;
        var d5 = document.getElementById("reYears").value;

        var zone = document.getElementById("license");
        var fees = document.getElementById("class");

        alert(d3);
        alert(d4);


        const exDate = new Date(d1);
        const reDate = new Date(d2);
        const diff = Math.abs(reDate - exDate);
        // const years = Math.abs(diff / (365 *60 * 60 * 24));
        // const months = Math.abs(diff - years * 365 *60 * 60 * 24 / (30 * 60 * 60 * 24));
        const days =Math.abs(diff/(1000 * 60 * 60 * 24));
        const months=Math.abs(days/30);

        if (months>1 && zone.value == "Contractor"){

            alert(months);
            alert("Your License Expired More than one month");

            if (d5.length == 0){
                alert("Please Enter Years")
            }
            else {
                var totalFees = Math.abs((+fees1) + (+d3) * d5);

                document.getElementById("totalFees").innerHTML=totalFees;

            }
        }
        else if (months<1 && zone.value == "Contractor"){

            alert(months);
            alert("Your License Expired Less than one month");

            var totalFees = Math.abs((+fees1) + (+d4));

            document.getElementById("totalFees").innerHTML=totalFees;
        }
        else if (months>12 && zone.value == "Supervisor"){
            alert("Your License Expired Less than one month")

            var totalFees = Math.abs((+fees1) + (+d3) * d5);

            alert(totalFees);

            document.getElementById("totalFees").innerHTML=totalFees;
        }
        else if (months<12 && zone.value == "Supervisor"){
            alert("Your License Expired Less than one month")

            var totalFees = Math.abs((+fees1) + (+d4));

            alert(totalFees);

            document.getElementById("totalFees").innerHTML=totalFees;
        }
        else if (months>12 && zone.value == "Electrician"){
            alert("Your License Expired Less than one month")

            var totalFees = Math.abs((+fees1) + (+d3) * d5);

            alert(totalFees);

            document.getElementById("totalFees").innerHTML=totalFees;
        }
        else if (months<12 && zone.value == "Electrician"){
            alert("Your License Expired Less than one month")

            var totalFees = Math.abs((+fees1) + (+d4));

            alert(totalFees);

            document.getElementById("totalFees").innerHTML=totalFees;
        }

    }



</script>
</body>
</html>

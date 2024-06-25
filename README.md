Created a CMS (Course Management System) in which students can check their results.

<br>
Sample Data: MANAV JAISWAL,111000 | AYUSH SHARMA, 111001 | SHANTANU SHAH, 111002

<br>
Using HTML, CSS, JS.

<br>
the same can be created throung backend code using Express, Node and HTML.

<br>
for that code as follows: 
const express = require("express")<br>
require("fs")<br>
const fs = require("fs")<br>
app = express()<br>
app.listen(4000,start)<br>
function start() {
    console.log("server started at port 8000")
}<br>
function home(req,res){
  res.sendFile(__dirname+"/result.html")
}<br>
function result(req,res){
    x=req.query.roll;
    y=req.query.name;<br>
    fs.writeFile("checked.txt","Checked: Name: "+y+"Roll No. "+x +"\n",{flag: 'a+'}, cnf)<br>
  if(x==111000 && y=="MANAV JAISWAL"){
    res.sendFile(__dirname+"/result_manav.html")
 }<br>
 else if(x==111001 && y=="SHANTANU SHAH"){
    res.sendFile(__dirname+"/result_shantanu.html")
 }<br>
 else if(x==111002 && y=="AYUSH SHARMA"){
   res.sendFile(__dirname+"/result_ayush.html")
 }
}
function cnf(){
   console.log("Data stored in txt file")
}
app.get("/",home)<br>
app.get("/data",result)<br>

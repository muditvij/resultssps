Created a CMS (Course Management System) in which students can check their results.
Sample Data: MANAV JAISWAL,111000 | AYUSH SHARMA, 111001 | SHANTANU SHAH, 111002
Using HTML, CSS, JS the same can be created throung backend code using Express, Node and HTML.
for that code as follows: 
const express = require("express")
require("fs")
const fs = require("fs")
app = express()
app.listen(4000,start)
function start() {
    console.log("server started at port 8000")
}
function home(req,res){
  res.sendFile(__dirname+"/result.html")
}
function result(req,res){
    x=req.query.roll;
    y=req.query.name
    fs.writeFile("checked.txt","Checked: Name: "+y+"Roll No. "+x +"\n",{flag: 'a+'}, cnf)
  if(x==111000 && y=="MANAV JAISWAL"){
    res.sendFile(__dirname+"/result_manav.html")
 }
 else if(x==111001 && y=="SHANTANU SHAH"){
    res.sendFile(__dirname+"/result_shantanu.html")
 }
 else if(x==111002 && y=="AYUSH SHARMA"){
   res.sendFile(__dirname+"/result_ayush.html")
 }
}
function cnf(){
   console.log("Data stored in txt file")
}
app.get("/",home)
app.get("/data",result)

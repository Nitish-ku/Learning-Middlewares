# Learning-Middlewares for the first time 

import express from "express";

# dirname is a directory extractor which returns a weird address

import { dirname } from "path";

# fileURLToPath converts the weird address format into a normal understandable address that you can use 

import { fileURLToPath } from "url";

# import.meta.data is the javascript way of giving you the address of your current javascript file but as a weird URL address 
# fileURLToPath converts this weird URL address into a regular file path address 
# dirname (...) takes the regular file path and  extracts just the directory path (the folder path) from it

const __dirname = dirname(fileURLToPath(import.meta.url));

const app = express();
const port = 3435;

app.get("/", (req,res)=>{
    res.sendFile(__dirname + "/index.html");
});

app.listen(port, ()=>{
    console.log(`Server running on port: ${port}`)
});

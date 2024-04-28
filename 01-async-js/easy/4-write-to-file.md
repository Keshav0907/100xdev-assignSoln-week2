## Write to a file
Using the fs library again, try to write to the contents of a file.
You can use the fs library to as a black box, the goal is to understand async tasks.
fs.readFile("a.txt",'utf-8',(err,data)=>{
  console.log(data);
})

fs.writeFile("a.txt",'Hello World',(err)=>{
  console.log("File  Written");
})
fs.appendFile('a.txt', 'First line added!', 'utf-8', err => {
  if (err) {
    throw err;
  }
  console.log('First line written.');
  fs.appendFile('a.txt', '\nSecond line appended.', err => {
    if (err) {
      throw err;
    }

    console.log('Second line appended.');
  });
});
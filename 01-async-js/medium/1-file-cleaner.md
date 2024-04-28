## File cleaner
Read a file, remove all the extra spaces and write it back to the same file.

For example, if the file input was
```
hello     world    my    name   is       raman
```

After the program runs, the output should be

```
hello world my name is raman
```

const fs = require("fs");

console.log("Before Trimming!!");

fs.readFile("a.txt", "utf-8", (err, data) => {
  console.log(data);
});

function removeSpaces() {
  fs.readFile("a.txt", "utf-8", (err, data) => {
    let content = data;
    newString = content.replace(/\s+/g, " ").trim();
    console.log(newString);
    fs.writeFile("a.txt", newString, (err) => {
      console.log("File  Written");
    });
  });
}

removeSpaces();

console.log("After trimming!");

fs.readFile("a.txt", "utf-8", (err, data) => {
  console.log("data");
});



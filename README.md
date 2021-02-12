# aproposavro

(WARNING: This is an extremely simple and unpolished tool- I haven't optimized this yet for user-friendliness)

Minimal web page to test avro schemas by parsing them. Once successfully parsed, you can then generate fake data based off them. You can also put in your own data to test against the parsed schema.

It tests the data by serializing it and then deserializing it. You'll see a success message in the browser console if the test is successful.

You can see any errors in either parsing, testing, or generating in the browser console.

Runs fully in your browser- there is no back-end.

## To use

1. Open index.html
2. paste your schema into the text area
3. Click the parse button. If successful, you'll see the parsed schema printed below the text area. If not, you'll see errors in the browser console.
4. (Optional) Click Generate Test Data (Warning: may not work for recursive schema definitions) Test data will appear in the second text area
5. (Optional) Paste your own test data into the second text area or use/modify the generated test data. Then click the Test Data button at the bottom of the screen and check the browser console for success or error

## To compile the dependencies yourself
Run the following commands:
```
npm install
npx browserify jsf-node.js -o jsf.js
npx browserify avsc.js -o avsc.js
npx browserify a2j.js -o avro2jsonschema.js
```
then go into the code for each generated file, find the code that corresponds to that of the un-browserified code, and put the variable into the global scope. Then open up index.html

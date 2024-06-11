# node.js-typescript

# Setting Up a Node.js Project with TypeScript

Install Node.js: Make sure you have Node.js installed. You can download it from the official website.

2. Initialize a new Node.js project:

```bash
mkdir my-node-project
cd my-node-project
npm init -y
```

3. Install TypeScript and necessary tools:

```bash
npm install typescript ts-node @types/node --save-dev
```

4. Create a tsconfig.json file:
   This file will configure the TypeScript compiler options.

```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "outDir": "./dist",
    "rootDir": "./src"
  },
  "include": ["src"],
  "exclude": ["node_modules"]
}
```

5. Create a simple TypeScript file:
   Create a directory named src and add a file named index.ts with the following content:

```bash
const sayHello = (name: string): string => {
  return `Hello, ${name}!`;
};

console.log(sayHello("World"));

```

6. Run the TypeScript file:
   You can use ts-node to run TypeScript files directly.

```bash
npx ts-node src/index.ts
```

7. Compile TypeScript to JavaScript:
   To compile the TypeScript files to JavaScript, use the TypeScript compiler:

```bash
npx tsc
```

This will generate JavaScript files in the dist directory as specified in tsconfig.json.

8. Run the compiled JavaScript:

```bash
node dist/index.js
```

# Additional Tips

. Linting: Use ESLint with TypeScript for code quality.

```bash
npm install eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin --save-dev
```

. Create a .eslintrc.json file:

```json
{
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "project": "./tsconfig.json"
  },
  "plugins": ["@typescript-eslint"],
  "extends": ["eslint:recommended", "plugin:@typescript-eslint/recommended"]
}
```

. Testing: Use a testing framework like Jest with TypeScript support.

```bash
npm install jest ts-jest @types/jest --save-dev
npx ts-jest config:init

```

Build Automation: Use tools like npm scripts or Gulp for automating tasks.

By following these steps, you will set up a Node.js project with TypeScript, enabling you to leverage TypeScript's type safety and advanced features while building server-side applications with Node.js.

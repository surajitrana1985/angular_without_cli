# angular_without_cli
This project is built on ANGULAR 5 without cli

Prerequisite:

NPM (Node Package Manager) should be installed

Steps:

1. create package.json using command:
     npm init -y

2. install packages such as core-js zone.js rxjs and systemjs using node command:
    npm install core-js zone.js rxjs systemjs -save

3. create a file namely systemjs.config.js under the root of the application

4. install angular packages such as @angular/core, @angular/compiler, @angular/common, @angular/platform-browser and @angular/platform-browser-dynamic using node command:
    npm install @angular/core @angular/compiler @angular/common @angular/platform-browser @angular/platform-browser-dynamic -save

5. update systemjs.config.js with the installed package paths as under:

    System.config({
        map: {
            app: 'dist/app',
            'zone.js': 'node_modules/zone.js',
            'rxjs': 'node_modules/rxjs',
            '@angular/core': 'node_modules/@angular/core/bundles/core.umd.js',
            '@angular/common': 'node_modules/@angular/common/bundles/common.umd.js',
            '@angular/compiler': 'node_modules/@angular/compiler/bundles/compiler.umd.js',
            '@angular/platform-browser': 'node_modules/@angular/platform-browser/bundles/platform-browser.umd.js',
            '@angular/platform-browser-dynamic': 'node_modules/@angular/platform-browser-dynamic/bundles/platform-browser-dynamic.umd.js'
        },
        packages: {
            'dist/app': {},
            'rxjs': {},
            'zone.js': {}
        }
    });

6. install typescript by using command:
    npm i --save-dev typescript

7. create a file tsconfig.json under root so as to configure typescript and make the below configurations:
    {
        "compilerOptions": {
            "outDir": "dist",
            "module": "commonjs",
            "moduleResolution": "node",
            "experimentalDecorators": true,
            "emitDecoratorMetadata": true,
            "lib": [
                "dom",
                "es2015"
            ]
        }
    }

8. change the below line in package.json 
    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1"
    },

    to

    "scripts": {
        "build": "tsc"
    },

    then run the below command to verify:

    npm run build

9. now create the src folder under root and create app folder and inside that create component and follow this source code

10. after creating all the files, run the command: npm run build. This will convert all typescript files into native javascript which browsers can read

11. install npm live-server by using command:
    npm i --save-dev live-server

    alternatively you can also use webpack too

12. now add an entry in package.json to run the live-server
    "scripts": {
        "build": "tsc",
        "start": "live-server"
    },

13. run commands:
    npm run build
    npm start

14. go to http://localhost:8080 and finally your angular is set up without cli.
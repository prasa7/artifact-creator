# artifact-creator
This app can use to create update artifacts and the script to run in the console.

copy the jar files and updated product to the same location as the gen.js script file and unzip them.

If you list the files and folder, it should look like bellow.

gen.js                                                
org.wso2.carbon.apimgt.publisher.feature-6.6.163/     
org.wso2.carbon.apimgt.store.feature-6.6.163/         
wso2am-3.1.0/

Update the params in the gen.js according to the patch info similar to bellow.

( You can uncomment web apps according to the list of web apps your patching )

For an example following config is only checking the publisher and devportal webapps.


// ******************************************************** //
// ******************************************************** //
// ******************************************************** //
//          This part need to modified accordingly          //
    const jars = [
    {
        jarName: 'org.wso2.carbon.apimgt.publisher.feature-6.6.163',
        appContext: 'publisher',
    },
    {
        jarName: 'org.wso2.carbon.apimgt.store.feature-6.6.163',
        appContext: 'devportal',
    },
    // {
    //     jarName: 'org.wso2.carbon.apimgt.admin.feature-6.6.163',
    //     appContext: 'admin',
    // }
]


const productName = 'wso2am-3.1.0';
const artifactFolderName = '0390';


// ******************************************************** //
// ******************************************************** //
// ******************************************************** //

You need to have node 10+ version installed.

> node gen.js

running above will create the artifact folder and it also gen a script file to run in the browser console to add the files during PR analysis.

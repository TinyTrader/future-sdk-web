# Integration Guide for Web

## Ways for integration
   webview or iframe
## Environment
   #### Test or development:
    http://x.chimchim.top/
   #### Production
   provides by yourself. 
## Integration
   integration by iframe:
   
       <iframe
           title="SDK"
           src='http://x.chimchim.top/perpetual?lang=en-US&5fu3=xxOi&vicolor=623DA2&theme=light&timezone=Asia/Kolkata'
           frameBorder="0"
           height="100%"
           width="100%"
           id="SDK"
           allowfullscreen="true"
           webkitallowfullscreen="true"
           mozallowfullscreen="true"
       />
   
  
   
   |Parameter|Type|Optional|Default|Notes|
   |---|---:|---:|---:|---:|
   |5fu3|string|Require||Channel ID(created by TinyTrader)|
   |sfg6|string|Optional||jwttoken|
   |lang|string|Optional|'en-US'|Language (Chinese zh-CN, Korean ko-KR, English: en-US. Default is en-US)|
   |theme|string|Optional|'light'|Theme color (dark: ‘dark’ mode ,light: ‘light’ mode. Default is light)|
   |vicolor|string|Require||VI color (if the VI color is #666666, you only need to pass the string 666666)|
   |timezone|string|Optional|Asia/Shanghai|(Asia/Kolkata, America/New_York, etc,defatult is Asia/Shanghai)|
   
## Interactive
   Copy the following code into your public component,these methods should be implemented in your app.
   
   
       window.addEventListener(
            "message",
            function (e) {
                const result =typeof e.data === "string" ? JSON.parse(e.data) : false;
                if (!result) return;
                switch (result.perpetualType) {
                    case "login": // After received this message, jump to the login page
                        break;
                    case "register": // After received this message, jump to the registration page
                        break;
                    case "transfer": // After received this message, jump to the fund transfer page
                        break;
                    case "token401": // After received this message, jump to the login page
                        break;

                }
            },
            false
        );

# Integration Guide for Web

## Ways for integration
   webview or iframe
## Environment(Domain)
   #### Test/Development:
       Domain: http://x.chimchim.top
       URL: http://x.chimchim.top/perpetual?5fu3=xxxx&vicolor=xxxx
   #### Production:
       Domain: https://yourDomain
       URL: https://yourDomain/perpetual?5fu3=xxxx&vicolor=xxxx
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
   |5fu3|string|Require||Channel ID(Provided by TinyTrader)|
   |sfg6|string|Optional||jwttoken|
   |lang|string|Optional|'en-US'|Language,Possible Values: zh-CN, ko-KR, en-US|
   |theme|string|Optional|'light'|Possible Values: dark,light|
   |vicolor|string|Require||VI color (if the VI color is #666666, you only need to pass the string 666666)|
   |timezone|string|Optional|Asia/Shanghai|Possible Values: 'America/New_York' , 'America/Los_Angeles' , 'America/Chicago' , 'America/Phoenix' , 'America/Toronto', 'America/Vancouver' , 'America/Argentina/Buenos_Aires' , 'America/El_Salvador' , 'America/Sao_Paulo' , 'America/Bogota' , 'America/Caracas' , 'Europe/Moscow' , 'Europe/Athens' , 'Europe/Belgrade' , 'Europe/Berlin' , 'Europe/London' , 'Europe/Luxembourg' , 'Europe/Madrid' , 'Europe/Paris' , 'Europe/Rome' , 'Europe/Warsaw' , 'Europe/Istanbul' , 'Europe/Zurich' , 'Australia/Sydney' , 'Australia/Brisbane' , 'Australia/Adelaide' , 'Australia/ACT' , 'Asia/Almaty' , 'Asia/Ashkhabad' , 'Asia/Tokyo' , 'Asia/Taipei' , 'Asia/Singapore' , 'Asia/Shanghai' , 'Asia/Seoul' , 'Asia/Tehran' , 'Asia/Dubai' , 'Asia/Kolkata' , 'Asia/Hong_Kong' , 'Asia/Bangkok' , 'Asia/Chongqing' , 'Asia/Jerusalem' , 'Asia/Kuwait' , 'Asia/Muscat' , 'Asia/Qatar' , 'Asia/Riyadh' , 'Pacific/Auckland' , 'Pacific/Chatham' , 'Pacific/Fakaofo' , 'Pacific/Honolulu' , 'America/Mexico_City' , 'Africa/Cairo' , 'Africa/Johannesburg' , 'Asia/Kathmandu' , 'US/Mountain'|
   
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


# Apple_Music_Authenticator

<!DOCTYPE html>
        <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Apple Music Authentication</title>
            <script type="text/javascript">
                function authenticateAppleMusic() {
                    var music = MusicKit.configure({
                        developerToken: 'eyJhbGciOiJFUzI1NiIsImtpZCI6IkRaQUtMMzI2TTgiLCJ0eXAiOiJKV1QifQ.eyJpc3MiOiI2RjI3VThXR1c4IiwiaWF0IjoxNzIzODUzNzE3LCJleHAiOjE3Mzk2MzA3MTd9.sdC9KFNtKxSMLDkF8XXuWe_zNYstt6Hx5AfCGGZE_wAUZK6G9s_nwS45jDZ6aIzuH3uAna3_14LfioXhtoMJzw',
                        app: {
                            name: 'Siren Music',
                            build: '1.0'
                        }
                    });

                    music.authorize().then(function(musicUserToken) {
                        console.log('Authorization successful, token: ' + musicUserToken);
                        // Send the token back to the app
                        window.location.href = 'callback://?token=' + musicUserToken;
                    }).catch(function(error) {
                        console.log('Authorization failed', error);
                    });
                }
            </script>
        </head>
        <body onload="authenticateAppleMusic()">
            <h1>Apple Music Authentication</h1>
            <p>Please wait while we authenticate you...</p>
        </body>
        </html>

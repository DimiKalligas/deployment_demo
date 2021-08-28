# firebase hosting
npm install -g firebase-tools
firebase login
firebase init
public directory -> build
configure as single-page app
firebase deploy
για να κατεβάσουμε τη σελίδα: firebase hosting:disable

# Στήσιμο express server: 
για τα routes που δεν είναι υπεύθυνος ο express: forward this route to React:
In server/index.js: 
if (process.env.NODE_ENV === ‘production’) { // automatically set by HEROKU
	// serve production assets
	app.use(express.static(‘client/build’))

	// if express does not recognize the route, serve index.html
	const path = require(‘path’)
    app.get(‘*’, (req, res) => {
        res.sendFile(path.resolve(__dirname, ‘client’, ‘build’, ‘index.html’)
    })
}

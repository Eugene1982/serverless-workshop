# Setup React App

Install and start your react app:

```
npx create-react-app sls-react
cd sls-react
npm run start
```

Note: Good time to commit.

Another Note: if you have a port clash locally, you can set the `PORT` environment variable to another port.

## Connect to your service

Lets add some logic to interact with our serverless api:

Open `src/App.js`

Add a lifecycle method to the `App` class to initiate a fetch:

```
  componentDidMount() {
    fetch('http://localhost:3000/hello')
      .then(res => res.json())
      .then(data => this.setState({data}));
  }
```

Note: your local serverless api **PORT**

You will also need to add a constructor with an initial state:

```
class App extends Component {
  constructor() {
    super();

    this.state = {
      data: null
    }
  }
...
```

Now lets replace the render method to respond to our state:

```
  render() {
    const { data } = this.state

    return (
      <div className="App">
        <header className="App-header">
          <h1 className="App-title">{!data ? 'loading...' : data.message }</h1>
        </header>
      </div>
    );
  }
```

*Why do this?* We need to update the render method so we can visually see our component render data that has been fetched from our lambda service.

You should now be able to see the message, from your lambda, displayed in your browser.

Assuming all is working; Another good moment to commit.

## Build and Deploy with Serverless

Lets install a plugin to do the heavy lifting:

```
npm install --save-dev serverless-finch
```

We need to update our serverless config so it is aware of the our `serverless-finch` plugin and our configuration on how we want to upload our SPA:

1. Add serverless-finch to the list of plugins
```
plugins:
  - ...
  - serverless-finch
```

2. Add custom configuration:
```
custom:
  client:
    bucketName: 101-ways-serverless-workshop-spa
    distributionFolder: dist
    indexDocument: index.html
```

## TODO

- [ ] Build app instructions
- [ ] Finish Deploy app instructions
- [ ] simple config for dev vs prod
- [ ] Dry-run
- [ ] Further reading ...
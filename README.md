# Kanban

## Big Picture

Last developer from your job was an undisciplined guy. He was writing bad code, ugly code, not following good practices and not working enough time to finish the project. He even did not take a shower some days. As a consecuense he got fired.

And you were recluted.<br />
You have two days to finish the project and send it on Sunday 18, March, 10PM.

But don’t worries. You have the code from last developer, but you’ll need to refactor and create the necessary components.

## The Assignment

Use `create-react-app` to create a new project and create the necessary React components to finish the project.

At least, you’ll need the next components:
1. `App`
2. `Header`
3. `Board`
4. `List`
5. `Card`

The `markup`, `styles` and `data` are below:

#### `App.js`
```js
class App extends Component {
  render() {
    return (
      <div>
        <Header />
        <section>
          <div className='board'>
            <div className='board__form container'>
              <form>
                <div className='form'>
                  <input ref='newItem' className='form__text' type='text' placeholder='Add new item...' />
                  <button className='form__submit' type='submit'>Add new</button>
                </div>
              </form>
            </div>
            <Board />
          </div>
        </section>
      </div>
    );
  }
}
```

#### `Header.js`
```js
class Header extends Component {
  render() {
    return (
      <header>
        <div className='header'>
          <div className='container'>
            <div className='grid'>
              <div>
                <p>Mr. Robot Notebook</p>
              </div>
              <div>
                <span>Loggued as <strong>Mr. Know it All</strong></span>
                <a href='#' className='header__link'><strong>Log out</strong></a>
              </div>
            </div>
          </div>
        </div>
      </header>
    );
  }
}
```

#### `Board.js`
```js
class Board extends Component {
  render() {
    return (
      <div className='container grid'>
        <List />
      </div>
    );
  }
}
```

#### `List.js`
```js
class List extends Component {
  render() {
    return (
      <article className='card'>
          <header>
            <div className='grid'>
              <strong className='card__title'>To Do</strong>
              <span className='card__quantity'>120 tasks</span>
            </div>
            <ul className='card__content'>
              <Card />
            </ul>
          </header>
        </article>
    );
  }
}
```

#### `Card.js`
```js
class Card extends Component {
  render() {
    return (
      <li className='card__item'>
        <p>Issue #3. No API Authentication Endpoint.</p>
        <small className='card__legend'>.internal</small>
        <button className='card__action'>
          <i className='fa fa-times'></i>
        </button>
      </li>
    );
  }
}
```

#### `App.css`
```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  font-family: 'Roboto';
  font-size: 14px;
  background-color: #f0f0f0;
}

.container {
  width: 85%;
  margin: 0 auto;
}

.header {
  background-color: #2a68e0;
  color: #dde5f9;
  padding: 20px;
  height: 100px;
}
.header__link {
  color: white;
  text-decoration: none;
  margin-left: 25px;
}

.grid {
  display: flex;
  justify-content: space-between;
}

.board__form {
  margin-top: -22px;
}

.card {
  font-size: 12px;
  border-radius: 3px;
  width: 30%;
  margin-top: 30px;
}
.card__title {
  color: #3f3f3f;
}
.card__quantity {
  color: #b0b0b0;
}
.card__content {
  background-color: white;
  font-size: 12px;
  list-style-type: none;
  margin: 0;
  padding: 0;
  color: #808080;
  border: 1px solid #d7d7d7;
  height: 65vh;
  overflow: scroll;
}
.card__item {
  background-color: white;
  padding: 20px 15px;
  border-bottom: 1px solid #d7d7d7;
  position: relative;
}

.card__item:hover .card__action {
  display: block;
}

.card__item p {
  font-size: 13px;
  line-height: 1.4;
}
/*
.card .card__item:last-of-type {
  border-bottom: 0;
}
*/
.card__legend {
  color: #b7b7b7;
}

.form {
  background-color: white;
  border-radius: 4px;
  display: flex;
  padding: 4px;
}
.form__text {
  border: 0;
  height: 36px;
  flex: 1;
  padding: 0 5px;
}
.form__text:focus {
  outline: none;
}
.form__submit {
  background: linear-gradient(#3e7df6, #235bc8);
  border: 0;
  text-transform: uppercase;
  color: white;
  font-size: 11px;
  letter-spacing: 1px;
  font-weight: bold;
  width: 100px;
  text-align: center;
  border-radius: 2px;
}

.card__action {
  border: 1px solid #D4D4D4;
  background: linear-gradient(#F9F9F9, #D3D3D3);
  border-radius: 2px;
  color: #898989;

  position: absolute;
  top: 10px;
  right: 15px;
  display: none;
}

.card__action:focus {
  outline: none;
}

p {
  margin: 0;
}
```

#### `data.js`
```js
export default [{
  key: 1,
  title: 'To Do',
  tasks: [{
    key: 1,
    title: 'New mobile application for iOS and Android. Versions for phones and tablets.',
    tagged: '.client'
  }, {
    key: 2,
    title: 'Prepare quote for website development for Netflix Company.',
    tagged: '.client'
  }, {
    key: 3,
    title: 'Prepare assets and source files for developers with new ToDo web application',
    tagged: '.internal'
  }, {
    key: 4,
    title: 'Create design of case studies for clients.',
    tagged: '.internal'
  }]
}, {
  key: 2,
  title: 'In Progress',
  tasks: [{
    key: 1,
    title: 'Prepare copy for case study ASDF',
    tagged: '.internal'
  }, {
    key: 2,
    title: 'Configure new Magento store and implement payments.',
    tagged: '.client'
  }, {
    key: 3,
    title: 'Prepare quote for website development for client AwesomeCompany and some longer title for task.',
    tagged: '.internal'
  }]
}, {
  key: 3,
  title: 'Done',
  tasks: [{
    key: 1,
    title: 'Create design of case studies for clients.',
    tagged: '.internal',
    done: true
  }, {
    key: 2,
    title: 'Push mobile application to App Store and Google Play.',
    tagged: '.client',
    done: true
  }, {
    key: 3,
    title: 'Final tests of ToDo web application.',
    tagged: '.internal',
    done: true
  }, {
    key: 4,
    title: 'Prepare invoices for clients.',
    tagged: '.internal',
    done: true
  }, {
    key: 5,
    title: 'Create design of case studies for clients.',
    tagged: '.internal',
    done: true
  }, {
    key: 6,
    title: 'Create design of case studies for clients.',
    tagged: '.internal',
    done: true
  }, {
    key: 7,
    title: 'Push mobile application to App Store and Google Play.',
    tagged: '.client',
    done: true
  }, {
    key: 8,
    title: 'Final tests of ToDo web application.',
    tagged: '.internal',
    done: true
  }, {
    key: 9,
    title: 'Prepare invoices for clients.',
    tagged: '.internal',
    done: true
  }, {
    key: 10,
    title: 'Create design of case studies for clients.',
    tagged: '.internal',
    done: true
  }]
}];
```

## Work Required

- You need to add the functionality to the form. It should work with an Enter pressed key on a click in the “Add new button”.
  - Hint: Check `onSubmit` event in the form.
- When a user add text in the input and press Enter key, that item should be displayed only in the **To Do** list.
  - Hint: You can handle these changes with `this.setState({})`
- If you put your cursor over each card it should display a button. Add the correct functionality to the event click, so, every time a user click that button the card should be deleted.

## Explorer Mode
- Add a condition in the input, and ask to the user which is the tag that will be attached to the new item, it could be only two: “.internal or .client”.
- Display the tag in the card, like it’s done.

## Adventure Mode
- Add the possibility to **Drag and Drop** cards between lists.
  - Hint: Check on Google which library could be useful for this kind of activity.

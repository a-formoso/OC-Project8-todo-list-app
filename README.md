# To-do List Application

## OpenClassrooms: Front-end Web Developer, Project 8

### Project deliverables

* Hunt and fix the bugs
* Add tests to support the project
* Analyse website performance
* Write technical documentation


### Author

#### By [*Alexandre Formoso*](https://aformoso.dev) - February 2020

### Preview application 
#### :point_right: [https://alexandreformoso.github.io/OC-Project8-todo-list-app/](https://alexandreformoso.github.io/OC-Project8-todo-list-app/)
Alternatively
* Run npm install
* Open the *index.html* file

![game printscreen](/img/to-do-img.png)

### Example Code
```javascript

/*global app, $on */

(function () {
	'use strict';

	/**
	 * Sets up a brand new Todo list.
	 *
	 * @param {string} name The name of your new to do list.
	 */
	function Todo(name) {
		this.storage = new app.Store(name);
		this.model = new app.Model(this.storage);
		this.template = new app.Template();
		this.view = new app.View(this.template);
		this.controller = new app.Controller(this.model, this.view);
	}

	var todo = new Todo('todos-vanillajs');

	function setView() {
		todo.controller.setView(document.location.hash);
	}
	$on(window, 'load', setView);
	$on(window, 'hashchange', setView);
})();



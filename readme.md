valstrap
========

Angular validation directives for Bootstrap forms.

# Install

```
bower install valstrap
```

# Directives included

All directives must be declared as attributes

* `val-form` - must be declared on the `<form>` element
* `val-model` - must be declared on each individual input element (and each input must use ng-model)
* `val-group` - declare it on the `form-group` wrapper element. Will add or remove the `has-error` class as appropriate
* `val-error` - can be assigned an optional error name to filter on (see examples below). Otherwise will default to showing on `required`

# Example Usage

``` html
    <form class="form-horizontal" role="form" name="form" novalidate val-form ng-submit="save()">
        <fieldset>
            <div class="form-group" val-group>
                <label for="inputTitle" class="col-lg-2 control-label">Title</label>
                <div class="col-lg-8">
                    <input type="text" name="title" ng-model="model.title" required ng-minlength="3" ng-maxlength="50" val-model
                           class="form-control" id="inputTitle" placeholder="Title" autocomplete="off">
    
                    <p val-error="required" class="help-block">Title is required.</p>
                    <p val-error="minlength" class="help-block">Please enter at least 3 characters.</p>
                    <p val-error="maxlength" class="help-block">Title is too long.</p>
                </div>
            </div>
            <div class="form-group" val-group>
                <label for="inputDescription" class="col-lg-2 control-label">Description</label>
                <div class="col-lg-8">
                    <textarea class="form-control" ng-model="model.description" required rows="3" id="inputDescription" val-model></textarea>
                    <p val-error class="help-block">Description is required.</p>
                </div>
            </div>
            <div class="form-group">
                <div class="col-lg-10 col-lg-offset-2 buttons">
                    <button type="submit" class="btn btn-primary">Save</button>
                </div>
            </div>
        </fieldset>
    </form>
```

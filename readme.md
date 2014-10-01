valstrap
========

Angular validation directives for Bootstrap forms.

# Install

```
npm install valstrap
```

# Directives included

* `val-form`
* `val-model`
* `val-group`
* `val-error`

# Example Usage

''' html
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
'''

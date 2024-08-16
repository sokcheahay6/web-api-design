# Web API design:

## Defend against Cross Site Request Forgery
Any operation that makes change to database must use POST method.
This requirement helps defending against Cross Site Request Forgery attack.

## Multiple Postings Safe (MPS)
Posting the same data multiple times must be safe and the action must be executed only one time.
For example, a user submitted a form, but the network is slow. After a long wait, he refreshes the page.
That data must have request id or any information to identify the same data and ensure that the actual work is executed only time.

## dashboard
Return a page showing information and links to available actions on entity.
Specify what will be return: nothing, or id, or the whole object, or anything.
Specify the format of those actions's result (json or anything else).
May provide option to select a format for the result.

## GET /entity/dashboad
The [dashbord](#dashboard) for entity.

## GET /entity/create
Return a page with form to enter data necessary for creating new entity.

## POST /entity/create
Return error if it already exists.
Create new entity with the form data.
Return the newly created entity in the specified format.

## GET /entity/list
Return a page with form to enter parameters for list operation.

## POST /entity/list
Return the entity list in the specified format.

## GET /entity/with-id/:id/dashboad
The [dashbord](#dashboard) for entity with the specify id.

## GET /entity/with-id/:id/get
Return a page with template to show the entity.
Usually, another POST request is used to get data to fill this template.

## POST /entity/with-id/:id/get
Return error if not found.
Return the entity in the specified format.

## GET /entity/with-id/:id/update
Return a page with form to enter data necessary for updating the entity.

## POST /entity/with-id/:id/update
Return error if not found.
Update the entity.
Return the updated entity in the specified format.

## GET /entity/with-id/:id/delete
Return a page with form to enter data necessary for deleting the entity.

## POST /entity/with-id/:id/delete
Return error if not found.
Delete the entity.
Return the specified result.

# Feedback Resources API

Retrieve feedbacks resource.

## List of feedbacks

#### Url
`/feedback`

#### Method
`GET`

### Description

Retrieve a list of feedbacks.

### Parameters

- string `status`
  > filter list by feedback status
- string `project`
  > filter list by project
- string `language`
  > filter list by language

### Sorting

- string `added`
  > order by feedback time

### Output
``

## feedback

#### Url
`/feedback/:id`

#### Method
`GET`

### Description

Retrieve `id` feedback resource

### Parameters

none

### Output
``

## create feedback

#### Url
`/feedback`

#### Method
`POST`

### Description

Create new feedback

### Parameters

- string `url`
  > url of the page
- string `locale`
  > translated string language
- string `screenshot`
  > base64 encoded image content
- int `project` (optional)
  > project id in onesky
- string `email` (optional)
  > user email to reply
- string `comment` (optional)
  > comment on feedback

### Output
``

## update feedback

#### Url
`/feedback/:id`

#### Method
`POST`

### Description

Update `id` feedback resource

### Parameters

- string `status`
  > change feedback status
- int `project`
  > associate with project id
- string `comment`
  > comment on feedback

### Output
``

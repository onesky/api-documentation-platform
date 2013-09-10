# Feedback Resources API

Retrieve feedback blocks resource.

## List of feedback blocks

#### Url
`/feedback/block`

#### Method
`GET`

### Description

Retrieve a list of feedback blocks.

### Parameters

- string `feedback`
  > filter list by feedback
- string `feedback_category`
  > filter list by feedback category
- string `project`
  > filter list by project
- string `language`
  > filter list by language

### Sorting

- string `added`
  > order by feedback time

### Output
``

## feedback blocks

#### Url
`/feedback/block/:id`

#### Method
`GET`

### Description

Retrieve `id` feedback block resource

### Parameters

none

### Output
``

## create feedback blocks

#### Url
`/feedback/block`

#### Method
`POST`

### Description

Create new feedback block

### Parameters

- string `category`
  > feedback category
- string `type`
  > feedback block type, either `string` or `non-textual`
- array `id`
  > for type `non-textual`, id marked on screenshot
- array `strings`
  > for type `string`, feedback string array
- string `comment` (optional)
  > comment on feedback block
- string `suggestion` (optional)
  > suggestion on feedback

### Output
``

## update feedback blocks

#### Url
`/feedback/block/:id`

#### Method
`POST`

### Description

Update `id` feedback block resource

### Parameters

- string `status`
  > change feedback block status

### Output
``

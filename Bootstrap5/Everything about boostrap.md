# Everything about bootstrap

What is Bootstrap?

Bootstrap is a free front end framework for easier and faster web development.

We can insert this in html file to use Bootstrap.(Content Delivery Network)

```html
<!-- Latest compiled and minified CSS -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet">

<!-- Latest compiled JavaScript -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js"></script>
```

## Container

`.container-fluid` : full width container

`.container` : Fixed width container, always centered in the screen

#### Difference between when there is a container and there isn't a container

<img width="1291" alt="image" src="https://user-images.githubusercontent.com/96529477/213251746-f7a18479-8223-4ad0-b176-10beaf117798.png">

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js"></script>

    <title>Document</title>
</head>
<body>  
    <div class="row">
        <div class="col text-center bg-info m-1 p-1">millionaire</div>
        <div class="col text-center bg-danger m-1 p-1">millionaire</div>
        <div class="col text-center bg-success m-1 p-1">millionaire</div>
    </div>
    
    <div class="container">
        <div class="row">
            <div class="col text-center bg-info m-1 p-1">millionaire</div>
            <div class="col text-center bg-danger m-1 p-1">millionaire</div>
            <div class="col text-center bg-success m-1 p-1">millionaire</div>
        </div>
    </div>
</body>
</html>
```

#### `.col-*` means `.col-xs-*`

First we need to figure out how the div looks like on a extra small viewport.

For example, 

```html
<div class="col-12">div</div>
```

means that we want `div` to take all 12 grids on extra small or higher number of screen.

#### What does this mean?

```html
<div class="col-lg-3 col-md-6 col-sm-3 text-center bg-primary">div</div>
<div class="col-lg-3 col-md-6 col-sm-3 text-center bg-success">div</div>
<div class="col-lg-3 col-md-6 col-sm-3 text-center bg-warning">div</div>
<div class="col-lg-3 col-md-6 col-sm-3 text-center bg-danger">div</div>
```

It means, when div class is larger than 960px, its size takes up to 3/12, when it is larger than 768px, size is 6/12, and when it is larger than 576px, it is 3/12.

The following code looks like this.

<img width="1553" alt="Screenshot 2023-01-18 at 11 07 52 AM" src="https://user-images.githubusercontent.com/96529477/213260686-21b88933-538a-46e7-bbff-fdf516a2fcc5.png">
<img width="1553" alt="Screenshot 2023-01-18 at 11 08 12 AM" src="https://user-images.githubusercontent.com/96529477/213260783-c4bd2c96-7d13-46de-8625-965700bbe07e.png">
<img width="1553" alt="Screenshot 2023-01-18 at 11 09 23 AM" src="https://user-images.githubusercontent.com/96529477/213260821-99b77029-562a-41f7-a4d4-df0c10458af6.png">
<img width="1553" alt="Screenshot 2023-01-18 at 11 09 35 AM" src="https://user-images.githubusercontent.com/96529477/213260846-820aa39a-6371-4535-bab1-ebb05363564f.png">


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js"></script>

    <title>Document</title>
</head>
<body>  
    <div class="container mt-5">
        <div class="row">
            <div class="col-lg-3 col-md-6 col-sm-3 text-center bg-primary">div</div>
            <div class="col-lg-3 col-md-6 col-sm-3 text-center bg-success">div</div>
            <div class="col-lg-3 col-md-6 col-sm-3 text-center bg-warning">div</div>
            <div class="col-lg-3 col-md-6 col-sm-3 text-center bg-danger">div</div>
        </div>
    </div>
</body>
</html>
```



This table shows when they become responsive.

|                |Extra small <576px|Small ≥576px|Medium ≥768px|Large ≥992px|Extra Large ≥1200px|XXL ≥1400px|
| -------------- | ---------------- | -----------| ------------| -----------| ------------------| ----------|
| max-width(sm)  |        100%      |    540px   |    720px    |    960px   |        1140px     |    1320px |
| .container-md  |        100%      |    100%    |    720px    |    960px   |        1140px     |    1320px |
| .container-lg  |        100%      |    100%    |     100%    |    960px   |        1140px     |    1320px |
| .container-xl  |        100%      |    100%    |     100%    |    100%    |        1140px     |    1320px |
| .container-xxl |        100%      |    100%    |     100%    |    100%    |        100%       |    1320px |

### Padding

Containers usually have left and right padding,

`.pt-5` : large top padding

### Border, background color, text color

`.border` : creates a border on the container

`. bg-dark` , `. bg-primary` : dark means black, primary is blue, they color the background in the container

`.text-white` : any text inside the container is colored white

### How to type tags faster

To type this, 

```html
<blockquote class="blockquote"></blockquote>
```

We can type `blockquote.blockquote`

To type this,

```html
<footer class="blockquote-footer"></footer>
```

We can type `footer.blockquote-footer`

### Text alignment

`.text-start` : left aligned text

`.text-end` : right aligned text

`.text-center` : center aligned text

### Table

### Cards

```html
<div class="card">
    <div class="card-header">card-header</div>
    <div class="card-body">card-body</div>
    <div class="card-footer">card-footer</div>
</div>
```

```html
<div class="container mt-3" style="width:300px">
    <div class="card">
        <img src="" alt="picture goes here" class="card-image-top rounded-top">
        <div class="card-body">
            <h2 class="card-title"><a href="#">card-title</a></h2>
            <div class="card-text">card-text</div>
            <a href="" class="btn btn-primary mt-3">button click</a>
        </div>
    </div>
</div>
```

Yii2 Masonry ListView Widget
======================

ListView widget improved to use as Masonry (http://masonry.desandro.com/)

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist nerburish/yii2-masonry-view": "dev-master
```

or add

```
nerburish/yii2-masonry-view": "dev-master
```

to the require section of your `composer.json` file.


Usage
-----

The usage is similar to default ListView Widget (http://www.yiiframework.com/doc-2.0/yii-widgets-listview.html)

You just need a dataProvider and prepare the item template for your model.

In clientOptions you can pass the Masonry options to modify the plugin behavior (see http://masonry.desandro.com/options.html)

You can also attach a cssFile for styling the grid.

Exemple:

We have this model:

class MyModel extends \yii\base\Theme
{
	public $id;
	
	public $title;
	
	public $description;
}

And this item template named _item.php:

<h3><?= $model->title ?></h3>
<p><?= $model->description ?></p>

Then in our view, we run the widget:

<?php echo \nerburish\masonryview\MasonryView::widget([
	'dataProvider' => $dataProvider,
	'itemView' => '_item',
	'clientOptions' => [
	  'gutterWidth' => 15,
	],
	'cssFile' => [
		"@web/css/masonry-demo.css"		
	]
]) ?>

The css used for the demo:

/* ---- grid ---- */
.grid {
  box-sizing: border-box;
}

/* clearfix */
.grid:after {
  content: '';
  display: block;
  clear: both;
}

/* ---- grid-item ---- */
.grid-item {
  width: 20%;
  padding: 10px;  
  margin: 10px auto;
  float: left;
  background: #e4e4e4;
  border-radius: 5px;
}





 
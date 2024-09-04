<?php snippet('header') ?>

<?php

// function that returns the formatted date
$callback = function($p) {
  return $p->date()->toDate('Y');
};
// group items using $callback
$groupedItems = page('notes')->children()->listed()->group($callback)->flip() ;

// output items by year
foreach($groupedItems as $year => $itemsPerYear): ?>
<p><b><?= $year ?></b></br>
  <?php foreach($itemsPerYear->flip() as $item): ?>
      <a href="<?= $item->url() ?>"><?= $item->title() ?></a>
      <time><?= $item->date()->toDate('F jS') ?></time>
    <?php endforeach; ?>
</p>
<?php endforeach ?>

<?php snippet('footer') ?>

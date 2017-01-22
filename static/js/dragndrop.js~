

var isAdvancedUpload = function() {
  var div = document.createElement('div');
  return (('draggable' in div) || ('ondragstart' in div && 'ondrop' in div)) && 'FormData' in window && 'FileReader' in window;
}();
var $form = $('.box');

if (isAdvancedUpload) {
  $form.addClass('has-advanced-upload');
}
if (isAdvancedUpload) {

  var droppedFiles = false;

  $form.on('drag dragstart dragend dragover dragenter dragleave drop', function(e) {
    e.preventDefault();
    e.stopPropagation();
  })
  .on('dragover dragenter', function() {
    $form.addClass('is-dragover');
  })
  .on('dragleave dragend drop', function() {
    $form.removeClass('is-dragover');
  })
  .on('drop', function(e) {
    droppedFiles = e.originalEvent.dataTransfer.files;
    document.getElementById('file').files=droppedFiles;
    $form.trigger('submit');
  });
//var $input    = $form.find('input[type="file"]')
//$input.on('change', function(e) { // when drag & drop is NOT supported
//  $form.trigger('submit');
//});
}
$form.on('submit', function(e) {
  if ($form.hasClass('is-uploading')) return false;
  $form.addClass('is-uploading').removeClass('is-error');
});




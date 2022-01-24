    <meta http-equiv="Content-type" content="text/html; charset=utf-8">
    <meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no">
    <title>BACKUP</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.3.1/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/5.0.1/css/bootstrap.min.css">
    <link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.11.3/css/dataTables.bootstrap5.min.css">    
    <script type="text/javascript" language="javascript" src="https://code.jquery.com/jquery-3.5.1.js"></script>
    <script type="text/javascript" language="javascript" src="https://cdn.datatables.net/1.11.3/js/jquery.dataTables.min.js"></script>
    <script type="text/javascript" language="javascript" src="https://cdn.datatables.net/1.11.3/js/dataTables.bootstrap5.min.js"></script>
    <script>const addButtons = settings => {
  $('#dt1 tr td:nth-child(1)').html(function() {
    return `<button type="button" title="google search" class="py-0 btn btn-secondary btn-sm search">${this.innerText}</button>`
  })
  $('#dt1 tr td:nth-child(2)').html(function() {
    return `<button type="button" title="google trends" class="py-0 btn btn-secondary btn-sm search">${this.innerText}</button>`
  })
    $('#dt1 tr td:nth-child(3)').html(function() {
    return `<button type="button" title="RB Check" class="py-0 btn btn-secondary btn-sm search">${this.innerText}</button>`
  })
};

$(document).ready(function() {
	//Create links for all keywords to Google Search result
  $('tbody td:nth-child(1)').on("click", ".search", function() {
    window.open(`https://google.com/search?q=${this.innerText}`, '_blank');
  })
  //Create links for all trend keywords to Google Trend 
  $('tbody td:nth-child(2)').click(function() {
    window.open(`https://trends.google.com/trends/explore?date=now 7-d&geo=US&q=${this.innerText}`, '_blank');
  })
  $('tbody td:nth-child(3)').click(function() {
    window.open(`https://www.redbubble.com/shop/?query=${this.innerText}`, '_blank');
  })

	//Create a Datatable with sorting, search and pagination opties
  $table = $('table').DataTable({
    "drawCallback": addButtons
  })
});


</script>

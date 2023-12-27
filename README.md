# js-export-table-data-in-csv-
js export table data in csv  in the larsavel project i used 
and this is a button 
<button  class="btn btn-primary sm" onclick="ExportToExcel('xlsx')">Export to Excel</button>
in thhis code u can only be change table id in function and than execute this code this coed work and help to download a csv file 
<script type="text/javascript" src=" https://unpkg.com/xlsx@0.15.1/dist/xlsx.full.min.js "></script>
<script>
      function ExportToExcel(type, fn, dl) {

                var elt = document.getElementById('add-products');
                var wb = XLSX.utils.table_to_book(elt, {
                    sheet: "sheet1"
                });
                var currentDate = new Date();
                var day = currentDate.getDate().toString().padStart(2, '0');
                var month = (currentDate.getMonth() + 1).toString().padStart(2, '0');
                var year = currentDate.getFullYear();
                var formattedDate = day + '-' + month + '-' + year;
                var fileName = 'GRN Product (' + formattedDate + ').xlsx';

                return dl ?
                    XLSX.write(wb, {
                        bookType: type,
                        bookSST: true,
                        type: 'base64'
                    }) :
                    XLSX.writeFile(wb, fn || fileName);
            }
</script>

document.getElementsByClassName("track-PrintPackingSlips")[0].addEventListener("click", function() {
    document.getElementsByClassName("lnk-add-tag")[0].click();
});


for (var k = 0; k < 2; k++) {
    document.getElementsByClassName("btn-ship")[k].addEventListener("click", function() {
        var i = 0;

        function  checkModalSuccess() {
            setTimeout(function(){
                if (document.getElementsByClassName("btn-ship").length === 3) {
                    document.getElementsByClassName("btn-ship")[2].addEventListener("click", function () {
                        function  checkLabelSuccess() {
                            var j = 0;

                            setTimeout(function(){
                                if (document.getElementsByClassName("btn-ship").length !== 3) {
                                    document.getElementsByClassName("lnk-scan-barcode")[0].click();
                                } else if (j >= 20) {
                                    return;
                                }
                                else {
                                    j++;
                                    checkLabelSuccess();
                                }
                            }, 50);
                        }
                        checkLabelSuccess();
                    })
                } else if (i >= 10) {
                    i++;
                    return;
                }
                else {
                    checkLabelSuccess();
                }
            }, 50);
        }
        checkModalSuccess();
    });
}

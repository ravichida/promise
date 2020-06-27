# Promise
Simple Promise Example

function getJSON(resource) {
            const promise = new Promise((resolve, reject) => {
                const URL = "https://jsonplaceholder.typicode.com/" + resource + "/";
                var jqxhr = $.getJSON(URL, function (data) {
                    resolve(data);
                }).done(function (data) {
                    resolve(data);
                }).fail(function (jqxhr, textStatus, error) {
                    var err = textStatus + ", " + error;
                    console.log("Request Failed: " + err);
                    reject(err);
                });
            });

            promise.then(
                function (data) {
                    addDataTable(data)
                },
                function (error) {
                    errorMsg(error);
            });
}

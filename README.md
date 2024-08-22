document.addEventListener("DOMContentLoaded", function() {
    const video = document.getElementById("video");
    const scanButton = document.getElementById("scanButton");
    const resultDiv = document.getElementById("result");

    // Access webcam
    if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
        navigator.mediaDevices.getUserMedia({ video: true }).then(function(stream) {
            video.srcObject = stream;
            video.play();
        });
    }

    // Simulate scan and result
    scanButton.addEventListener("click", function() {
        // Simulate random results for demonstration
        const isSafe = Math.random() > 0.5;
        
        if (isSafe) {
            resultDiv.textContent = "Water is safe to drink.";
            resultDiv.className = "result safe";
        } else {
            resultDiv.textContent = "Water is not safe to drink.";
            resultDiv.className = "result unsafe";
        }
    });
});

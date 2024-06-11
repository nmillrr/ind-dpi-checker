var minDPI = Number(prompt("Enter the minimum acceptable DPI:", "300")); 
if (isNaN(minDPI) || minDPI <= 0) { 
    alert("Please enter a valid number greater than 0."); 
} else { 
    var linkedImages = app.activeDocument.allGraphics; 
    var results = []; 
    for (var i = 0; i < linkedImages.length; i++) { 
        var image = linkedImages[i]; 
        if (image instanceof Image) { 
            var effectivePPI = image.effectivePpi; 
            if (effectivePPI[0] < minDPI || effectivePPI[1] < minDPI) { 
                results.push({ 
                    name: image.itemLink.name, 
                    ppi: effectivePPI[0] + " x " + effectivePPI[1] + " DPI" 
                });
            } 
        } 
    } 
    if (results.length > 0) { 
        var message = "The following images have an effective PPI below " + minDPI + " DPI:\n\n"; 
        for (var j = 0; j < results.length; j++) { 
            message += results[j].name + ": " + results[j].ppi + "\n"; 
        } 
        alert(message); 
    } else { 
        alert("All images meet the minimum acceptable DPI of " + minDPI + " DPI."); 
    } 
} 

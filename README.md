<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Animal Company JSON Bot</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f0f0f0;
      padding: 20px;
    }
    h1 {
      text-align: center;
    }
    #bagList {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 20px;
    }
    .bag {
      background-color: #fff;
      border: 1px solid #ccc;
      padding: 10px;
      cursor: pointer;
      flex: 1 1 200px;
      text-align: center;
    }
    .bag:hover {
      background-color: #e0e0e0;
    }
    #selectedBags {
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>Animal Company JSON Bot</h1>
  <button id="startButton">Start Add Bag</button>
  <div id="bagList" style="display: none;"></div>
  <div id="selectedBags"></div>

  <script>
    const bags = [
      "Backpack",
      "Flashlight Backpack",
      "Small Backpack",
      "Hiking Backpack",
      "Large Clover Print Backpack",
      "Large Basketball Print Backpack",
      "Briefcase"
    ];

    const startButton = document.getElementById('startButton');
    const bagList = document.getElementById('bagList');
    const selectedBags = document.getElementById('selectedBags');

    startButton.addEventListener('click', () => {
      bagList.style.display = 'flex';
      bagList.innerHTML = '';
      bags.forEach(bag => {
        const bagDiv = document.createElement('div');
        bagDiv.className = 'bag';
        bagDiv.textContent = bag;
        bagDiv.addEventListener('click', () => {
          const bagItem = document.createElement('div');
          bagItem.textContent = bag;
          selectedBags.appendChild(bagItem);
        });
        bagList.appendChild(bagDiv);
      });
    });
  </script>
</body>
</html>

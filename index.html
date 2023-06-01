<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Mon jeu Phaser</title>
  <script src="//cdn.jsdelivr.net/npm/phaser@3.60.0/dist/phaser.min.js"></script>
  <style>
    body {
      margin: 0;
      padding: 0;
      overflow: hidden;
    }
  </style>

</head>
<body>

<script>
  // Création de la configuration du jeu
  const config = {
    type: Phaser.AUTO,
    width: 600,
    height: 700,
    scene: {
      preload: preload,
      create: create
    }
  };

  const game = new Phaser.Game(config);

  const costs = {
    vendeur: 15,
    cuisto: 20,
    parking: 25
  };

  function preload() {
    this.load.image('background', 'images/splash.jpg');
    this.load.image('backgroundImage', 'images/back_home.jpg');
    this.load.image('greenButton', 'images/gameui/greenRectNormal.png');
    this.load.image('blueRectTapped', 'images/gameui/blueRectTapped.png');
    this.load.image('pinkRectNormal', 'images/gameui/pinkRectNormal.png');
    this.load.image('pinkRectTapped', 'images/gameui/pinkRectTapped.png');
    this.load.image('greenBtnNormal', 'images/gameui/greenBtnNormal.png');
    this.load.image('greenBtnTapped', 'images/gameui/greenBtnTapped.png');
    this.load.image('greyRectNormal', 'images/gameui/greyRectNormal.png');
    this.load.image('greyRectTapped', 'images/gameui/greyRectTapped.png');
    this.load.audio('backgroundSound', 'sounds/background.wav');
    this.load.audio('click', 'sounds/click.wav');
    this.load.audio('lvlup', 'sounds/lvlup.wav');
    this.load.audio('spam', 'sounds/spam.wav');
  }

  // Fonction de création du contenu
  function create() {
    const screenWidth = this.sys.game.config.width;
    const screenHeight = this.sys.game.config.height;

    const background = this.add.image(0, 0, 'background').setOrigin(0);
    background.setScale(screenWidth / background.width, screenHeight / background.height);


    this.time.delayedCall(500, () => {
      this.scene.start('MainScene');
    }, [], this);
  }

  class MainScene extends Phaser.Scene {
    constructor() {
      super({ key: 'MainScene' });
      this.counter = 0;
      this.countCoffeeText = null;
      this.elements = [
        { key: 'vendeur', name: 'Vendeur', count: 0, speed:10 },
        { key: 'cuisto', name: 'Barista', count: 0, speed:25 },
        { key: 'parking', name: 'Parking', count: 0, speed:60 }
      ];
      this.textElements = {};
      this.nextIncrementTime = null;
      this.speed = 1000;
      this.clickSound = null;
      this.lvlUpSound = null;

    }

    create() {
      const music = this.sound.add('backgroundSound');
      music.play();

      const screenWidth = this.sys.game.config.width;
      const screenHeight = this.sys.game.config.height;

      const backgroundImage = this.add.image(0, 0, 'backgroundImage').setOrigin(0);
      backgroundImage.setScale(screenWidth / backgroundImage.width, screenHeight / (backgroundImage.height * 2));

      this.createTextElements();

      const greenBtnNormal = this.addButton(300, 175, 'greenBtnNormal', 'Go !', this.updateCounter);

      this.elements.forEach((element, index) => {
        const xPos = 90;
        const yPos = 400 + index * 60;
        this.createInteractiveButton(xPos, yPos, 'greyRectNormal', `buy${element.name}`, () => this.buyElement(element), element);
      });

      
      const clickSound = this.sound.add('click');
      this.clickSound = clickSound;

      const lvlUpSound = this.sound.add('lvlup');
      this.lvlUpSound = lvlUpSound;
    }

    createTextElements() {
      const bgCountCoffee = this.add.image(80, 30, 'blueRectTapped').setDisplaySize(150, 50);
      this.countCoffeeText = this.add.text(15, 20, `Compteur : ${this.counter}`, { font: '20px Arial', fill: '#ffffff' });
      this.countCoffeeText.setOrigin(0, 0);

      this.elements.forEach((element, index) => {
        const xPos = 500;
        const yPos = 30 + index * 60;
        const bgCountElement = this.add.image(xPos, yPos, 'blueRectTapped').setDisplaySize(150, 50);
        this.textElements[element.key] = this.add.text(xPos - 70, yPos - 10, `${element.name} : ${element.count}`, { font: '20px Arial', fill: '#ffffff' });
      });
    }

    addButton(x, y, key, text, onClick) {
      const button = this.add.image(x, y, key).setInteractive();
      button.setDisplaySize(100, 50);
      button.on('pointerdown', onClick, this);

      const buttonText = this.add.text(x - 30, y - 10, text, { font: '20px Arial', fill: '#ffffff' });
      return { button, buttonText };
    }

    createInteractiveButton(x, y, key, text, onClick, element) {
      const button = this.add.image(x, y, key).setInteractive().setDisplaySize(150, 50);
      console.log(button)
      button.on('pointerdown', () => {
        button.setTexture('pinkRectTapped');
        onClick.call(this, element);
      });
      button.on('pointerup', () => {
        button.setTexture(this.counter >= ((element.count + 1) * costs[element.key]) ? 'pinkRectNormal' : 'greyRectNormal');
      });

      const buttonText = this.add.text(x - 65, y - 10, `${element.name} : ${(element.count + 1) * costs[element.key]}`, { font: '20px Arial', fill: '#ffffff' });
      this.textElements[`buy${element.name}`] = {button, buttonText };
    }

    update(time, delta) {
      if (time > this.nextIncrementTime) {
        this.counterAuto();
        this.nextIncrementTime = time + this.speed; // Prochain moment pour incrémenter le compteur
      }
    }

    counterAuto() {
      // this.counter = Math.round(this.counter + (this.elements.reduce((total, element) => total + element.count, 0)));
      this.counter++;
      this.countCoffeeText.setText(`Compteur : ${this.counter}`);
      this.updateButtonStates();
    }

    updateCounter() {
      this.clickSound.play();
      this.counter++;
      this.countCoffeeText.setText(`Compteur : ${this.counter}`);
      this.updateButtonStates();
    }

    buyElement(element) {
      
      this.lvlUpSound.play();
      if(this.counter >= (element.count + 1) * costs[element.key]){
        this.updateCounterMinus((element.count + 1) * costs[element.key], element);
        element.count++;
        this.textElements[element.key].setText(`${element.name} : ${element.count}`);
        this.textElements[`buy${element.name}`].buttonText.setText(`${element.name} : ${(element.count + 2) * costs[element.key]}`);
      }
      this.speed -= element.speed;
    }

    updateCounterMinus(value, element) {
      this.counter -= value;
      this.countCoffeeText.setText(`Compteur : ${this.counter}`);
      this.updateButtonStates();
    }

    updateButtonStates() {
      this.elements.forEach((element) => {
        const button = this.textElements[`buy${element.name}`].button;
        this.counter >= ((element.count + 1) * costs[element.key]) ? button.setTexture('pinkRectNormal') : button.setTexture('greyRectNormal');
      });
    }
  }

  game.scene.add('MainScene', MainScene);
</script>

</body>
</html>

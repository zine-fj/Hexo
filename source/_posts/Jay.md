---
title: Jay
date: 2022-11-19 21:58:40
tags:
---
<style>
    * {
      margin: 0;
      padding: 0;
    }

    ul,
    li {
      list-style: none;
    }

    .jay-list {
      display: flex;
      flex-wrap: wrap;
    }

    .jay {
      display: inline-block;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
      padding: 20px;
      border-radius: 10px;
      margin: 0 30px 30px 0;
      cursor: pointer;
    }

    .jay:hover {
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
    }

    .jay .header {
      display: flex;
      margin-bottom: 20px;
    }

    .jay .cover {
      width: 130px;
      height: 130px;
      object-fit: cover;
      border-radius: 5px;
      margin-right: 20px;
    }

    .jay .intro {}

    .jay .intro .album {
      display: flex;
      margin: 10px 0;
    }

    .jay .intro .album-word {
      margin-right: 15px;
    }

    .jay .intro .name-cn {
      font-weight: bold;
      font-size: 18px;
      max-width: 200px;
    }

    .jay .intro .name-zn {
      font-size: 14px;
      font-weight: 400;
      color: rgb(149, 141, 141);
    }

    .jay .intro .singer {
      margin-bottom: 10px;
    }

    .jay .intro .time {}

    .jay .music-list {}

    .jay .music-list .music-li {
      display: flex;
      justify-content: space-between;
      margin-bottom: 10px;
    }
    .jay .music-list .music-li:hover {
      background-color: rgba(0,0,0,.04);
    }

    .jay .music-list .music-li .index {
      margin-right: 5px;
      font-size: 14px;
      width: 12px;
    display: inline-block;
    }

    .jay .music-list .music-li .name {
      font-size: 16px;
    }
    .jay .music-list .music-li .singer {
      font-size: 14px;
    }
  </style>

  <div class="jay-list" id="JayList"></div>

  <script>
    const JayAlbumList = [
      {
        name: "周杰伦",
        time: "2000-11-07",
        title: "Jay",
        titleZN: "杰伦",
        cover: "../images/Jay/Jay.jpeg",
        musicList: [
          { name: "可爱女人", singer: "周杰伦" },
          { name: "完美主义", singer: "周杰伦" },
          { name: "星晴", singer: "周杰伦" },
          { name: "娘子", singer: "周杰伦" },
          { name: "斗牛", singer: "周杰伦" },
          { name: "黑色幽默", singer: "周杰伦" },
          { name: "伊斯坦堡", singer: "周杰伦" },
          { name: "印第安老斑鸠", singer: "周杰伦" },
          { name: "龙卷风", singer: "周杰伦" },
          { name: "反方向的钟", singer: "周杰伦" },
        ],
      },
    ];
    const jayListDom = document.getElementById("JayList");
    console.log("jayListDom: ", jayListDom);

    let listString = "";
    for (let i = 0; i < JayAlbumList.length; i++) {
      let item = JayAlbumList[i];

      listString = `<div class="jay">
                        <header class="header">
                          <img src="${item.cover}" alt="${item.title}" class="cover" />
                          <div class="intro">
                            <div class="album">
                              <div class="album-word">专辑:</div>
                              <div class="name-cn">${item.title} <span class="name-zn">(${item.titleZN})</span></div>
                            </div>
                            <div class="singer">
                              <span class="album-word">歌手:</span>${item.name}
                            </div>
                            <div class="time">
                              <span class="album-word">时间:</span>${item.time}
                            </div>
                          </div>
                        </header>
                        <ul class="music-list"></ul>
                      </div>`;
      jayListDom.innerHTML = listString;
      let musicListDom = document.getElementsByClassName("music-list")[0];
      console.log("musicListDom: ", musicListDom);
      let musicListString = "";
      for (let j = 0; j < item.musicList.length; j++) {
        let musicLi = item.musicList[j];

        let musicDom = document.createElement("div");
        musicListString = `<li class="music-li">
                              <div class="music-li-left">
                                <span class="index">${j + 1}</span>
                                <span class="name">${musicLi.name}</span>
                              </div>
                              <div class="singer">${musicLi.singer}</div>
                            </li>`;
        musicDom.innerHTML = musicListString;
        musicListDom.append(musicDom);
      }
    }
  </script>




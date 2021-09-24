# Book group UI with HTML, CSS and JS.
# Compatible browsers:
    Chrome, Edge, Firefox, Opera, Safari
# HTML :    
    <div class='container'>
    <div class='center list flex-column'>
      <div class='card flex-row open'>
        <img src='http://i.harperapps.com/covers/9780008108298/y450-293.jpg' class='book'>
        <div class='flex-column info'>
          <div class='title'>The Fellowship of the Ring</div>
          <div class='author'>J.R.R. Tolkien</div>
          <div class='hidden bottom summary'>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quod ratione impedit temporibus maiores autem aperiam                   assumenda exercitationem, quisquam nobis esse.
          </div>
        </div>
        <div class='flex-column group'>
          <div class='members'>
            <span class='current'>14</span> /
            <span class='max'>30</span>
          </div>
          <div class='hidden bottom'>
            <button class='simple'>Join</button>
          </div>
        </div>
      </div>
      <div class='card flex-row'>
        <img src='https://i.pinimg.com/originals/52/ec/12/52ec12f7dd324864949267c92cce2e43.jpg' class='book'>
        <div class='flex-column info'>
          <div class='title'>1984</div>
          <div class='author'>George Orwell</div>
          <div class='hidden bottom summary'>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quod ratione impedit temporibus maiores autem aperiam assumenda exercitationem, quisquam nobis esse.
          </div>
        </div>
        <div class='flex-column group'>
          <div class='members'>
            <span class='current'>14</span> /
            <span class='max'>30</span>
          </div>
          <div class='hidden bottom'>
            <button class='simple'>Join</button>
          </div>
        </div>
      </div>
      <div class='card flex-row'>
        <img src='https://images-na.ssl-images-amazon.com/images/I/51N5qVjuKAL._SX309_BO1,204,203,200_.jpg' class='book'>
        <div class='flex-column info'>
          <div class='title'>To Kill a Mockingbird</div>
          <div class='author'>Harper Lee</div>
          <div class='hidden bottom summary'>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quod ratione impedit temporibus maiores autem aperiam assumenda exercitationem, quisquam nobis esse.
          </div>
        </div>
        <div class='flex-column group'>
          <div class='members'>
            <span class='current'>14</span> /
            <span class='max'>30</span>
          </div>
          <div class='hidden bottom'>
            <button class='simple'>Join</button>
          </div>
        </div>
      </div>
      <div class='card flex-row'>
        <img src='https://upload.wikimedia.org/wikipedia/en/thumb/f/f7/TheGreatGatsby_1925jacket.jpeg/220px-TheGreatGatsby_1925jacket.jpeg' class='book'>
        <div class='flex-column info'>
          <div class='title'>Great Gatsby</div>
          <div class='author'>F Scott Fitzgerald</div>
          <div class='hidden bottom summary'>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Quod ratione impedit temporibus maiores autem aperiam assumenda exercitationem, quisquam nobis esse.
          </div>
        </div>
        <div class='flex-column group'>
          <div class='members'>
            <span class='current'>14</span> /
            <span class='max'>30</span>
          </div>
          <div class='hidden bottom'>
            <button class='simple'>Join</button>
          </div>
        </div>
      </div>
    </div>
    </div>
    
# CSS : 
          $dark:#131325;
      body {
        background-color:$dark;
      }
      .flex-row {
        display:flex;
        flex-flow:row;
        align-items:center;
      }
      .flex-column{
        display:flex;
        flex-flow:column;
      }
      .center {
          align-items:center;
        position:absolute;
        top:50%;
        left:50%;
        transform:translate(-50%,-50%);
      }
      .list {
        border-radius:3px;
        overflow:hidden;
        & .card {
          cursor:pointer;
          min-width:700px;
          margin-bottom:10px;
          perspective:600px;
          transition:all 0.1s;
          & .bottom {
            height:0px;
            overflow:hidden;
            width:200px;
            font-size:12px;
            color:#777;
            font-weight:normal;
          }
          &.open {
            padding:30px;
            height:auto;
            & .bottom {
              margin-top:10px;
              height:100%;
              overflow:visible;
            }
            & .book {
              transform:rotateY( 50deg );
              box-shadow:-10px 10px 10px 2px rgba(0,0,0,.2), -2px 0px 0px 0px #888;
              transition:all 0.5s;
              transition-delay:0.05s;
            }
            & .info {
              transform:translate(0,-10px);
            }
            & .members {
              padding:15px 20px;
              border-radius:4px;
              align-self:flex-start;
            }
          }
          & button.simple {
            cursor:pointer;
            color:#CCC;
            border:none;
            outline:none;
            border-radius:4px;
            background-color:#1ea94b;
            padding:15px 20px;
            font-family:'Montserrat';
            font-weight:bold;
            transition:all 0.1s;
            &:hover {
              box-shadow:0px 15px 20px -5px rgba(0,0,0,.3);
              transform:translate(0,-2px);
            }
          }
          background-color:lighten($dark,8%);
          box-shadow:0px 2px 10px rgba(0,0,0,.2);
          overflow:hidden;
          height:90px;
          & .book {
            transition:all 0.5s;
            width:120px;
            box-shadow:0px 2px 10px rgba(0,0,0,0.3);
            overflow:hidden;
          }
          & .info {
            transition:all 0.2s;
            min-width:200px;
            padding:0px 30px;
            font-family:'Montserrat';
            font-weight:bold;
            & .title {
              font-size:1em;
              color:#FFF;
              letter-spacing:1px;
            }
            & .author {
              font-size:12px;
              font-weight:normal;
              color:#888;
            }
          }
          & .group {
              margin-left:auto;  
          }
          & .members {

            transition:all 0.1s;
            padding:40px;
            font-family:'Montserrat';
            color:#CCC;
            background-color:lighten($dark,5%);
            & .current {
              font-weight:bold;
              margin-right:10px;
            }
            & .max {
              opacity:0.5;
              margin-left:10px;
            }
          }
        }
      }
      
 # JS : 
     let old = $('.card').get(0);
    $('.card').click(function(){
      if(old!=null && $(old).hasClass('open'))
        $(old).toggleClass('open');
       $(this).toggleClass('open');
       old = this;

    })
 


<?php

ob_start();
define( API_KEY , 5405615711:AAGLc0wXNRAr6DtTZbiT2TKc4MnubTquajM );
echo "https://api.telegram.org/bot".API_KEY."/setwebhook?url=".$_SERVER[ SERVER_NAME ]."".$_SERVER[ SCRIPT_NAME ];
function bot($method,$datas=[]){
    $url = "https://api.telegram.org/bot".API_KEY."/".$method;
$ch = curl_init();
    curl_setopt($ch,CURLOPT_URL,$url);
    curl_setopt($ch,CURLOPT_RETURNTRANSFER,true);
    curl_setopt($ch,CURLOPT_POSTFIELDS,$datas);
    $res = curl_exec($ch);
    if(curl_error($ch)){
        var_dump(curl_error($ch));
    }else{
        return json_decode($res);
    }
}



$update = json_decode(file_get_contents( php://input ));
$message = $update->message;
$chat_id = $message->chat->id;
$text = $message->text;
$chat_id2 = $update->callback_query->message->chat->id;
$message_id = $update->callback_query->message->message_id;
$data = $update->callback_query->data;
$from_id = $message->from->id;
$bot = bot( getme )->result->username;
$name = $update->message->from->first_name;
$from_id = $message->from->id;
$join = bot( getChatMember ,["chat_id"=>"@ssa_15","user_id"=>$from_id])->result->status;
if (!in_array($chat_id, explode("\n", file_get_contents( mem.txt )))) {
  file_put_contents( mem.txt , $chat_id."\n",FILE_APPEND);
}
if($message && $join ==  left ){
bot( sendMessage , [
 chat_id =>$chat_id,
 text =>"- عليك الاشتراك في القناة ليتم تشغيل البوت . 🚫",
 reply_markup =>json_encode([
   inline_keyboard =>[
    [[ text => • اشترك -🔱  , url => https://t.me/ssa_15 ]]
  ]
])
]);
die( مشيولي );
}
mkdir( po );
$ex = explode(   ,$text);
if($text ==  /start ){
    bot( sendMessage ,[
       chat_id =>$chat_id,
 text   =>"- مرحبا بك ، [$name](tg://user?id=$chat_id)
- في بوت الحصول على ارقام امريكية - ✅ 
• يقوم البوت بأعطائك رقم امريكي للتليجريام . . .
- قم بتجميع نقاط واحصل على رقم الان ؛⚜️",
 parse_mode =>"MarkDown",
 disable_web_page_preview =>true,
     reply_markup =>json_encode([
       inline_keyboard =>[
        [[ text => • الحصول على رقم ؛⚠️ , callback_data => getnum ]],
        [[ text => - تجميع نقاط ،🔘 , callback_data => geturl ],[ text => - معرفة نقاطك ،🔘 , callback_data => getpo ]],
        [[ text =>"• اضغط هنا وتابع جديدنا 🇮🇶؛",  url =>"https://t.me/ssa_15"]],        
      ]
      ])
    ]);
  
    } 
    if (isset($ex[1]) and $ex[0] ==  /start ) {
        bot( sendMessage ,[
       chat_id =>$chat_id,
 text   =>"- مرحبا بك ، [$name](tg://user?id=$chat_id)
- في بوت الحصول على ارقام امريكية - ✅ 
• يقوم البوت بأعطائك رقم امريكي للتليجريام . . .
- قم بتجميع نقاط واحصل على رقم الان ؛⚜️",
 parse_mode =>"MarkDown",
 disable_web_page_preview =>true,
     reply_markup =>json_encode([
       inline_keyboard =>[
        [[ text => • الحصول على رقم ؛⚠️ , callback_data => getnum ]],
        [[ text => - تجميع نقاط ،🔘 , callback_data => geturl ],[ text => - معرفة نقاطك ،🔘 , callback_data => getpo ]],
        [[ text =>"• اضغط هنا وتابع جديدنا 🇮🇶؛",  url =>"https://t.me/ssa_15"]],        
      ]
      ])
    ]);
    if (!in_array($chat_id, explode("\n", file_get_contents( po/ .$ex[1]. .txt )))) {
       file_put_contents( po/ .$ex[1]. .txt , $chat_id."\n",FILE_APPEND);
       bot( sendMessage ,[
         chat_id =>$ex[1],
         text => قام : @ .$message->from->username."\n بالدخول الى رابطك الخاص نقاطك هي : ".count(explode("\n", file_get_contents( po/ .$ex[1]. .txt )))
       ]);
    }
  }
if ($data ==  getnum ) {
  if (count(explode("\n", file_get_contents( po/ .$chat_id. .txt ))) < 25) {
      bot( answerCallbackQuery ,[
         callback_query_id =>$update->callback_query->id,
         text => عليك تجميغ 25 نقطه ؛🚫 ,
         show_alert =>true
      ]);
  } else {
    $r = rand(0,9999999999);
    bot( editMessageText ,[
       chat_id =>$chat_id2,
       message_id =>$message_id,
       text =>"• اليك رقمك ( $r ) \n قم بالتسجيل به وسيصلك الكود هنا ✅"
    ]);
    unlink( po/ .$chat_id2. .txt );
  }
}
if ($data ==  geturl ) {
  $api =  http://api.adf.ly/api.php? ;
  $query = [
     key  => 5e8c79c146837bfde948ef711b949658 ,
     uid  => 19279099,
     advert_type  =>  int ,
     domain  =>  adf.ly ,
     url  =>  https://t.me/ .$bot. ?start= .$chat_id2
  ];
  $api = $api . http_build_query($query);
  $api =  file_get_contents($api);
  bot( editMessageText ,[
     chat_id =>$chat_id2,
     message_id =>$message_id,
     text => - اليك رابطك الخاص (  .$api.  ) -✅
    قم بأرساله للمستخدمين وكل شخص يدخل سوف تحصل على نقطه واحده ✅ 
  ]);
}

# statement denying or limiting responsibili
免责声明
These resources are collected from the web
所有资产均为来自网络的整理
It is used only for study, testing
仅可用于学习和测试
If you want to commercialize these assets you can buy them in the store
如果你要商用请去商店购买资产
If any of these assets infringe on your interests, please contact me
如果侵害您的权益，请联系我


# [进入WIKI，开始寻找](https://github.com/IndiaGameMaker/UnityAsset/wiki/Assets "hello world")

![扫码_搜索联合传播样式-白色版](https://github.com/IndiaGameMaker/UnityAsset/assets/1924146/3b117a6b-81d6-472e-8070-06f31359f7d0)

工具

![image](https://github.com/IndiaGameMaker/UnityAsset/assets/1924146/e47804e4-49e4-4e45-8c7b-5cd2436eb533)

    
    DOTween.To(() => light.spotAngle, (x) =>
        {
            light.spotAngle = x;
        }, JumpDownDamgeRange, 1f);

==================================================================================
        
④   {//世界不存在的人
   
            string url = "https://thispersondoesnotexist.com/image";

            UnityWebRequest www = UnityWebRequestTexture.GetTexture(url);
            yield return www.SendWebRequest();

            if (www.result != UnityWebRequest.Result.Success )
            {
                Debug.Log(www.error);
            }
            else
            {
                Texture2D t = ((DownloadHandlerTexture)www.downloadHandler).texture;
                img.sprite = Sprite.Create(t, new Rect(0, 0, t.width, t.height), Vector2.zero);
            }

========================================================================================
        
               if (Physics.Raycast(Camera.main.ScreenPointToRay(Input.mousePosition), out var hitOver, 100, LayerMaskManager.Valet));

========================================================================================
        
    public static void Copy<T>(T source, out T destination) where T : class
    {
        System.Runtime.Serialization.Formatters.Binary.BinaryFormatter binaryFormatter = new System.Runtime.Serialization.Formatters.Binary.BinaryFormatter();
        MemoryStream stream = new MemoryStream();
        binaryFormatter.Serialize(stream, source);
        stream.Seek(0, SeekOrigin.Begin);
        destination = (T)binaryFormatter.Deserialize(stream);
        stream.Close();
        stream.Dispose();
    }

========================================================================================
        
    public static Vector2 WorldPosition2AnchoredPosition(Vector3 position)
    {
        if (!PublicConst.canvas || !PublicConst.UICamera) return Vector2.zero;
        position.z = 0;
        Vector2 pos;
        RectTransformUtility.ScreenPointToLocalPointInRectangle(PublicConst.canvas.transform as RectTransform, PublicConst.UICamera.WorldToScreenPoint(position), PublicConst.canvas.worldCamera, out pos);
        return pos;
    }
    public static Vector2 MousePosOnUGUI(Vector3 mousePosition)
    {
        Vector2 pos;
        RectTransformUtility.ScreenPointToLocalPointInRectangle(PublicConst.canvas.transform as RectTransform, mousePosition, PublicConst.canvas.worldCamera, out pos);
        return pos;
    }
    public static Vector2 WorldPosition2AnchoredPosition(RectTransform parent, Vector3 position)
    {
        position.z = 0;
        Vector2 pos;
        RectTransformUtility.ScreenPointToLocalPointInRectangle(parent, PublicConst.UICamera.WorldToScreenPoint(position), PublicConst.canvas.worldCamera, out pos);
        return pos;
    }
        

=======================================================================================
        
             private void 0nJoystickInput(Vector2 inputDir)
             {
                moveDir =new Vector3(inputDir.x,e,inputDir.y);if( moveDir.magnitude >0.01f)//如果有方向输入，人物就转向那个方向
                transform.rotation =Quaternion.Lerp(transform.rotation,Quaternion.LookRotation(_moveDir),Time.deltaTime*10)               
             }
              private void FixedUpdate()
              {
                transform.Translate( transform.InverseTransformDirection( moveDir)*Time.deltaTime*Movespeed);}
              }
              private void 0nJoystickInput(Vector2 inputDir)
              {
                moveDir= Quaternion.uler(8,camera.main.transform.localeulerAngles.y, 0)* new vector3(inputDir.x, 0, inputDir.y);
              }
              private void onJoystickInput(vector2 inputDir)
              {//这里选择在获取到输入的时候就改变动画的状态，然后在移动代码中判断动画的速度，确保跑的动画播放了人物再移动
                moveDir = Quaternion,Euler(0,camera,main,transform,localeulerAngles.y, 0)* new vector3(inputDir.x, 8, inputbir.y);
              }
              {//控制动画状态机混合树的值，0是ldle，1是全力奔跑
                animspeed= moveDir.maRnitude / 95f;//摇杆的半径为95
                animator.SetFloat( animSpeedHash,animSpeed);
                if(_moveDir.magnitude >8.01f)//如果有方向输入，人物就转向那个方向
                transform.rotation =Quaternion.Lerp(transform.rotation,quaternion,LookRotation( moveDir),Time.deltaTime*1@);
                private void Fixedupdate()
                if(_animspeed >8.05f)//先判新动画是否切换到跑步状态，确保人物没迈腿的时候不移动
                  transform.Translate( transform,InverseTransformDirection( moveDir)*Time,deltaTime*Movespeed);}
              //  3.3.2 移动更加丝滑由于之前写的摇杆逻辑，抬手之后输出的方向马上就变为了(0.0.0)，这会导致人物突然停下，为了得到更加丝滑的效果，这里的moveDir改用插值的方式获取，
                0nJovstickInput(vector2 inputDir)
                {
                  //将输入方向转换为xz平面移动的方向，需要根摄像机的朝向旋转方向
                  var targetDir = Quaternion.Euler(0,camera.main.transform.localEulerAngles.y, 8)* new Vector3(inputDir.x, 0, inputDir.z);//用插值是为了不让抬手的时候人物马上停下，有一个减速的过程
                  moveDir =vector3.Lerp( moveDir,targetDir,1e*Time.deltaTime);
                  //控制动画状态机混合树的值，8是Idle，1是全力奔跑
                  animspeed=moveDir.magnitude /95f;//摇杆的半径为95
                  animator.setFloat(animspeedHash,animspeed):if( moveDir.magnitude >8.81f)//如果有方向输入，人物就转向那个方向
                  transform,rotation =Quaternion,Lerp(transform,rotation,Quaternion,LookRotation( moveDir),Time.deltaTime*1e);if(moveDir.magnitude >95f)//限制移动速度
                  moveDir-moveDir.normalized *9sf;              
              }
             

=======================================================================================
        
                public static Texture2D MergeTexture(Texture2D src, Texture tex, SpriteAlignment alignment, Vector2Int offset)
 {
     if (tex == null)
     {
         return src;
     }
     RenderTexture previousRT = RenderTexture.active;

     RenderTexture srcCopy = RenderTexture.GetTemporary(src.width, src.height);
     Graphics.Blit(src, srcCopy);

     RenderTexture texCopy = RenderTexture.GetTemporary(tex.width, tex.height, 0);
     Graphics.Blit(tex, texCopy);

     var result = new Texture2D(src.width, src.height);
     RenderTexture.active = srcCopy;
     result.ReadPixels(new Rect(0, 0, src.width, src.height), 0, 0);
     result.Apply();
     RenderTexture.active = texCopy;

     switch (alignment)
     {
         case SpriteAlignment.Center:
             offset += new Vector2Int((src.width - tex.width) >> 1, (src.height - tex.height) >> 1);
             break;
         case SpriteAlignment.TopLeft:
             offset += new Vector2Int(0, src.height - tex.height);
             break;
         case SpriteAlignment.TopCenter:
             offset += new Vector2Int((src.width - tex.width) >> 1, src.height - tex.height);
             break;
         case SpriteAlignment.TopRight:
             offset += new Vector2Int(src.width - tex.width, src.height - tex.height);
             break;
         case SpriteAlignment.LeftCenter:
             offset += new Vector2Int(0, (src.height - tex.height) >> 1);
             break;
         case SpriteAlignment.RightCenter:
             offset += new Vector2Int(src.width - tex.width, (src.height - tex.height) >> 1);
             break;
         case SpriteAlignment.BottomLeft:
             offset += new Vector2Int(0, tex.height);
             break;
         case SpriteAlignment.BottomCenter:
             offset += new Vector2Int((src.width - tex.width) >> 1, tex.height);
             break;
         case SpriteAlignment.BottomRight:
             offset += new Vector2Int(src.width - tex.width, tex.height);
             break;
         case SpriteAlignment.Custom:
             break;
         default:
             break;
     }

     result.ReadPixels(new Rect(0, 0, tex.width, tex.height), offset.x, offset.y);
     result.Apply();
     RenderTexture.active = previousRT;
     RenderTexture.ReleaseTemporary(texCopy);

     return result;
 };

======================================================================================
        
    private EventTrigger.Entry GeneratorEntry(EventTriggerType eventTriggerType,UnityAction<BaseEventData> callBack)
    {
        EventTrigger.TriggerEvent triggerEvent = new EventTrigger.TriggerEvent();
        triggerEvent.AddListener(callBack);

        return new EventTrigger.Entry() { eventID = eventTriggerType, callback = triggerEvent };

    }

==================================================================================
"sv_label_1"是蓝色圆形的图标，对于其他图标，请查看这个所有Unity内置编辑器图标的详细列表https://github.com/halak/unity-editor-icons 
        
               var iconContent = EditorGUIUtility.IconContent("sv_label_1");
               EditorGUIUtility.SetIconForObject(gameObject, (Texture2D) iconContent.image);

===========================================================================


======================================================================================
        
 

        public static void AddEventTrigger(GameObject obj, EventTriggerType eventTriggerType, UnityAction<BaseEventData> callBack)
    {//Image,动态添加事件
        var et = obj.GetComponent<EventTrigger>();
        if (null == et)
        {
            et = obj.AddComponent<EventTrigger>();
        }
        EventTrigger.TriggerEvent triggerEvent = new EventTrigger.TriggerEvent();
        triggerEvent.AddListener(callBack);
        et.triggers.Add(new EventTrigger.Entry() { eventID = eventTriggerType, callback = triggerEvent });
    }

==================================================================================
  
======================================================================================
        
 、、权重

    public static int GetItemByWeight(Item[] itemsArr)
    {
        var sum = 0;
        foreach (var item in itemsArr) { sum += item.nWeight; }

        var random = Random.Range(0, sum);
        for (int i = 0; i < itemsArr.Length; i++)
        {
            if (random >= itemsArr[i].nWeight) { random -= itemsArr[i].nWeight; continue; }
            return itemsArr[i];
        }
        return 0;
    }

==================================================================================
  

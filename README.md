# FunGameRefreshView

[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-HitBlockRefresh-brightgreen.svg?style=flat)](http://android-arsenal.com/details/3/3253)


# Preview

<img src="preview/HitBlock.gif" width="350px" />
<img src="preview/BattleCity.gif"  width="350px" />

# FunGame

# Usage

    布局文件中：
    <com.hitomi.refresh.view.FunGameRefreshView
        android:id="@+id/refresh_hit_block"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:game_type="hit_block">
                
        <ListView
            android:id="@+id/list_view"
            android:layout_width="fill_parent"
            android:layout_height="fill_parent"
            android:scrollbars="none">
        </ListView>
        
    </com.hitomi.refresh.view.FunGameRefreshView>

    Activity中：
        refreshView = (FunGameRefreshView) findViewById(R.id.refresh_fun_game);
        listView = (ListView) findViewById(R.id.list_view);

        arrayAdapter = new ArrayAdapter<String>(this, android.R.layout.simple_expandable_list_item_1, createDate());
        listView.setAdapter(arrayAdapter);
        
        refreshView.setOnRefreshListener(new FunGameRefreshView.FunGameRefreshListener() {
            @Override
            public void onPullRefreshing() {
                // 模拟后台耗时任务
                SystemClock.sleep(2000);
            }

            @Override
            public void onRefreshComplete() {
                updateDataList();
                arrayAdapter.notifyDataSetChanged();
            }
        });
        

# Attributes

        <attr name="game_type" format="enum">
            <enum name="hit_block" value="0" />
            <enum name="battle_city" value="1" />
        </attr>

        <attr name="left_model_color" format="color" />
        <attr name="middle_model_color" format="color" />
        <attr name="right_model_color" format="color" />

        <attr name="mask_top_text" format="string" />
        <attr name="mask_bottom_text" format="string" />
        <attr name="text_loading" format="string" />
        <attr name="text_loading_finished" format="string" />
        <attr name="text_game_over" format="string" />

        <attr name="top_text_size" format="integer" />
        <attr name="bottom_text_size" format="integer" />

        <attr name="block_horizontal_num" format="integer" />
        <attr name="ball_speed" format="integer">
            <enum name="low" value="3" />
            <enum name="medium" value="6" />
            <enum name="fast" value="9" />
        </attr>


#Thanks


#Licence

MIT 




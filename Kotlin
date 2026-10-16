package com.example.myapplication

import android.os.Bundle
import android.view.View
import android.widget.Button
import android.widget.EditText
import android.widget.RadioButton
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    private var ed_name: EditText? = null
    private var tv_text: TextView? = null
    private var tv_name: TextView? = null
    private var tv_winner: TextView? = null
    private var tv_mmora: TextView? = null
    private var tv_cmora: TextView? = null
    private var btn_scissor: RadioButton? = null
    private var btn_stone: RadioButton? = null
    private var btn_paper: RadioButton? = null
    private var btn_mora: Button? = null

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // 連結 XML 的元件
        ed_name = findViewById<EditText>(R.id.ed_name)
        tv_text = findViewById<TextView>(R.id.tv_text)
        tv_name = findViewById<TextView>(R.id.tv_name)
        tv_winner = findViewById<TextView>(R.id.tv_winner)
        tv_mmora = findViewById<TextView>(R.id.tv_mmora)
        tv_cmora = findViewById<TextView>(R.id.tv_cmora)

        btn_scissor = findViewById<RadioButton>(R.id.btn_scissor)
        btn_stone = findViewById<RadioButton>(R.id.btn_stone)
        btn_paper = findViewById<RadioButton>(R.id.btn_paper)
        btn_mora = findViewById<Button>(R.id.btn_mora)

        // 設定猜拳按鈕的監聽事件
        btn_mora!!.setOnClickListener(View.OnClickListener { view: View? ->

            // 判斷是否輸入姓名
            if (ed_name!!.length() < 1) {
                tv_text!!.setText("請輸入玩家姓名")
            } else {
                // 顯示玩家姓名

                tv_name!!.setText(
                    String.format(
                        "名字\n%s",
                        ed_name!!.getText().toString()
                    )
                )

                // 判斷玩家出拳
                if (btn_scissor!!.isChecked()) {
                    tv_mmora!!.setText("我方出拳\n剪刀")
                } else if (btn_stone!!.isChecked()) {
                    tv_mmora!!.setText("我方出拳\n石頭")
                } else {
                    tv_mmora!!.setText("我方出拳\n布")
                }

                // 產生電腦亂數：0、1、2
                val computer_random = (Math.random() * 3).toInt()

                // 判斷電腦出拳
                if (computer_random == 0) {
                    tv_cmora!!.setText("電腦出拳\n剪刀")
                } else if (computer_random == 1) {
                    tv_cmora!!.setText("電腦出拳\n石頭")
                } else {
                    tv_cmora!!.setText("電腦出拳\n布")
                }

                // 判斷玩家獲勝
                if ((btn_scissor!!.isChecked() && computer_random == 2) ||
                    (btn_stone!!.isChecked() && computer_random == 0) ||
                    (btn_paper!!.isChecked() && computer_random == 1)
                ) {
                    tv_winner!!.setText(
                        "勝利者\n" + ed_name!!.getText().toString()
                    )
                    tv_text!!.setText("恭喜您獲勝了！")

                    // 判斷電腦獲勝
                } else if ((btn_scissor!!.isChecked() && computer_random == 1) ||
                    (btn_stone!!.isChecked() && computer_random == 2) ||
                    (btn_paper!!.isChecked() && computer_random == 0)
                ) {
                    tv_winner!!.setText("勝利者\n電腦")
                    tv_text!!.setText("可惜，電腦獲勝了！")

                    // 平手
                } else {
                    tv_winner!!.setText("勝利者\n平手")
                    tv_text!!.setText("平局，請再試一次！")
                }
            }
        })
    }
}

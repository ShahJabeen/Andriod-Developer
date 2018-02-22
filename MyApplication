package ca.sajiduleth.shahjabeen.myapplication;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.AdapterView;
import android.widget.ArrayAdapter;
import android.widget.Spinner;
import android.view.View;


public class MainActivity extends AppCompatActivity
{

    private EditText input1, input2;
    private TextView result;
    private Button equal;

    String[] ops = { "+", "-", "*", "/"};
    String opselected;
    double a,b,c;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        result = (TextView) findViewById(R.id.result);
        equal = (Button)findViewById(R.id.equal);
        input1 = (EditText)findViewById(R.id.input1);
        input1.setText("");
        input2= (EditText)findViewById(R.id.input2);
        input2.setText("");

        ops = getResources().getStringArray(R.array.val_array);
        Spinner s1 = (Spinner) findViewById(R.id.spinner1);
        ArrayAdapter<String> adapter = new ArrayAdapter<String>(this, android.R.layout.simple_spinner_item, ops);
        adapter.setDropDownViewResource(android.R.layout.simple_spinner_item);
        s1.setAdapter(adapter);

        s1.setOnItemSelectedListener(new AdapterView.OnItemSelectedListener() {
            @Override
            public void onItemSelected(AdapterView<?> arg0,
                                       View arg1, int arg2, long arg3) {
                int index = arg0.getSelectedItemPosition();
                opselected = ops[index];

                equal.setOnClickListener(new View.OnClickListener()
                {
                    public void onClick(View view)
                    {
                        // if value is not enetered then this message will be displayed
                        if (input1.getText().toString().isEmpty())
                            result.setText("Please Input Something");
                        // if value is not entered then this messgae will be displayed
                        else if (input2.getText().toString().isEmpty())
                            result.setText("PLease Input Something");
                        //else if (Integer.parseInt(EditText.getText().toString())> 100 )
                        else {
                            String inputa = input1.getText().toString();
                            a = Double.parseDouble(inputa);
                            String inputb = input2.getText().toString();
                            b = Double.parseDouble(inputb);

                            switch (opselected) {
                                case "+":
                                    c = a + b;
                                    result.setText(Double.toString(c));
                                    break;

                                case "-":
                                    c = a - b;
                                    result.setText(Double.toString(c));
                                    break;
                                case "*":
                                    c = a * b;
                                    result.setText(Double.toString(c));
                                    break;
                                case "/":
                                    c = a / b;
                                    // if Division by 0 is done then this message will be displayed
                                    if (b == 0) {
                                        result.setText("Division by zero is not allowed");
                                        break;
                                    }
                                    result.setText(Double.toString(c));
                                    break;
                                default:
                                    result.setText("Select an Option");
                            }
                        }
                    }
                });
            }
            @Override
            public void onNothingSelected(AdapterView<?> arg0) {
            }


        });

        }

    }

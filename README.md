# Ud3_Ejemplo9
_Ejemplo 9 de la Unidad 3._ 

Vamos a crear un _Floating Action Button (FAB)_ que cuando se pulse aparezca un mensaje por pantalla. 

Para ello primero lo incluimos en nuestro _layout_.

_activity_main.xml_:
```
...
    <android.support.design.widget.FloatingActionButton
        android:id="@+id/fab"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="end|bottom"
        android:layout_marginEnd="32dp"
        android:layout_marginRight="32dp"
        android:layout_marginBottom="32dp"
        android:src="@drawable/estrella"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />

</android.support.constraint.ConstraintLayout>
```
Y luego en la clase _MainActivity_ lo buscamos y le asignamos el evento asociado.

_MainActivity.java_:
```
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Buscamos el FAB y configuramos su onCliclListener
        FloatingActionButton fab = findViewById(R.id.fab);

        fab.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                Toast.makeText(MainActivity.this, "FAB", Toast.LENGTH_LONG).show();
            }
        });
    }
}
```

Para poder utilizar la clase _FloatingActionButton_ deberemos incluir la dependencia 
_com.android.support:design:28.0.0_ en el fichero _build.gradle(Module:app)_:
```
dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    implementation 'com.android.support:appcompat-v7:28.0.0'
    implementation 'com.android.support.constraint:constraint-layout:1.1.3'
    implementation 'com.android.support:design:28.0.0'
    ...
}
```

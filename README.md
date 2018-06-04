# dan
procedure TForm1.Button1Click(Sender: TObject);
var
x:real;

et:string;
e:char;
l,i:integer;

begin
  if RadioGroup1.ItemIndex=-1 then ShowMessage('Выберите что вам надо узнать')
  else
    begin
      if edit1.text='' then ShowMessage('Введите X')
      else
          begin
          x:=StrToFloat(edit1.Text);
            if RadioGroup1.ItemIndex=0 then
              begin
                if FRAC(X)=0 then
                  ShowMessage('Целое')
                else
                ShowMessage('Не целое');
              end;


            if RadioGroup1.ItemIndex=1 then
              begin
                if trunc(x)in[10..99] then
                  ShowMessage('Двузначное')
                else
                  ShowMessage('Не двузначное')
              end;


            if RadioGroup1.ItemIndex=2 then
              begin

               et:=edit1.text;
               e:=et[1];
               i:=1;
               l:=0;

                      if e in ['a'..'z']  then
                        begin
                         l:=1;
                        end
                     else
                      begin
                        if e in  ['A'..'Z'] then
                          begin
                            l:=1;
                          end;
                      end;
                 if l=0 then
                    ShowMessage('Не является лат.')
                else
                   ShowMessage('Является лат.')


              end;

          end;

    end;

end;

end.

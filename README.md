//선택 완료된 페이지에서 동명 추출 동명 추출
inputs = document.getElementById('dsForm').getElementsByTagName('input')
var inputarray = [];
for ( row in inputs )
{
	if (inputs[row].type=='hidden'&&inputs[row].name=='var3')
	{
		console.log(inputs[row].outerHTML)
		var tempString = inputs[row].outerHTML;
		var ts = tempString;
		var ds = ts.indexOf("\" nm=\"", 0)+1;
		var de = ts.indexOf("\"", ds)+1;
		var df = ts.indexOf("\"", de);
		var gs = ts.indexOf("\" data_nm=\"", 0)+1;
		var ge = ts.indexOf("\"", gs)+1;
		var gf = ts.indexOf("\"", ge);
		var vs = ts.indexOf("\" value=\"", 0)+1;
		var ve = ts.indexOf("\"", vs)+1;
		var vf = ts.indexOf("\"", ve);
		console.log(ds,de,df,gs,ge,gf,vs,ve,vf)
		inputarray[inputarray.length] = {
			'gu':ts.substring(de,df),
			'dg':ts.substring(ge,gf),
			'vl':ts.substring(ve,vf)
		}
	}
}
inputarray[0]


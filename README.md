PeopleWhoJAM
============

//CONSOLE
		//SEND the D3 Objecit to the Console
			console.log(d3);
//DATA01
		var dataArray = [20,40,50];
//DATA02
		var dataArray = [5,40,50,60];
		var width = 500;
		var height = 500;

		var widthScale = d3.scale.linear()
			.domain([0,60])
			.range([0,width]);
			
		var color =d3.scale.linear()
			.domain([0,60])
			.range(["red","blue"]);
//ELEMENTS
			//D3: Select Element, Append Child Element, Decorate Text Attribute
			//**D3: redundant rename, style-color			
			
			d3.select("body")
				.append("p")
				.text('Research Spike: D3 Flare iBloc peoplewhojam.wikispaces.com/data');

			d3.select("p")
				.text('Research Spike: D3 Flare iBloc peoplewhojam.wikispaces.com/data')
				.style("color", "red")
		//D3 SHAPES
			//D3: SVG
				var canvas = d3.select("body")
					.append("svg")
					.attr("width",500)
					.attr("height",500);
			//D3: Circle	
				var circle = canvas.append("circle")
					.attr("cx",250)
					.attr("cy",250)
					.attr("r",50)
					.attr("fill","red");
			//D3 Rectangle
				var rect = canvas.append("rect")
					.attr("width",100)
					.attr("height",50);
			//D3 Line
				var line = canvas.append("line")
					.attr("x1",0)
					.attr("y1",100)
					.attr("x2",400)
					.attr("y2",400)
					.attr("stroke","green")
					.attr("stroke-width",10);
//SHAPES(DATA01)
		var canvas = d3.select("body")
			.append("svg")
			.attr("width",500)
			.attr("height",500);


		var bars = canvas.selectAll("rect")
			.data(dataArray)
			.enter()
				.append("rect")
				.attr("width",function(d) { return d * 10;})
				.attr("height",50)
				.attr("y", function(d,i) { return i * 100;})
				;
///////
//SHAPES(DATA02)
		var canvas = d3.select("body")
			.append("svg")
			.attr("width",width)
			.attr("height",height);


		var bars = canvas.selectAll("rect")
			.data(dataArray)
			.enter()
				.append("rect")
				.attr("width",function(d) { return widthScale(d);})
				.attr("height",50)
				.attr("fill", function (d) {return color(d) })
				.attr("y", function(d,i) { return i * 100;})
				;
///////


ForEveryIdea

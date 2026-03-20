# Example Diagrams

Annotated XML samples from real AWS architecture diagrams. Use these as references for style, layout, and structure.

## Example 1: OpenSearch Trending Queries (Pipeline Layout)

**Architecture type**: Left-to-right data pipeline with Step Functions workflow group
**Key patterns**: Pipeline flow, Step Functions container, sub-resource icons (crawlers, catalogs), edge labels as child cells

### Prompt

Generate this diagram that shows a serverless architecture for identifying trending search queries, where user search logs flow through an API Gateway and streaming pipeline into S3, get processed and clustered by batch ETL jobs on a daily schedule, and then use an LLM to pick the most relevant trending query per cluster to display back on the search page. The system should include a real-time ingestion path with streaming and buffering, a batch processing path with crawlers and transformation jobs orchestrated by a scheduler, and a serving layer with a NoSQL database and API for surfacing trending queries to both end users and business analysts.

### Full XML

```xml
<mxfile host="Electron" agent="Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/29.3.6 Chrome/140.0.7339.249 Electron/38.8.0 Safari/537.36" version="29.3.6">
  <diagram name="Page-1" id="oTQwp31No7SUkpcENYgM">
    <mxGraphModel dx="1901" dy="2149" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0" background="#FFFFFF">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-14" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-1">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="249" y="350" />
            </Array>
            <mxPoint x="249" y="280" as="sourcePoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-41" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-33" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-39">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="1210" y="469" />
              <mxPoint x="1210" y="550" />
              <mxPoint x="437" y="550" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-3" parent="1" style="sketch=0;outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_aws_cloud;strokeColor=#858B94;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#858B94;dashed=0;" value="AWS" vertex="1">
          <mxGeometry height="890" width="1390" x="160" y="-260" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-7" edge="1" parent="1" source="ilInOXCaW5QfBG5FtNbR-1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-2">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="ilInOXCaW5QfBG5FtNbR-1" parent="1" style="shape=actor;whiteSpace=wrap;html=1;labelPosition=center;verticalLabelPosition=bottom;align=center;verticalAlign=top;" value="User" vertex="1">
          <mxGeometry height="60" width="50" y="189" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-1" parent="1" style="shape=actor;whiteSpace=wrap;html=1;labelPosition=center;verticalLabelPosition=bottom;align=center;verticalAlign=top;" value="Business Analyst" vertex="1">
          <mxGeometry height="60" width="50" y="300" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-8" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-4">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="250" y="10" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-50" connectable="0" parent="o_v1HXyxiM5dD5V4Gu-O-8" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];" value="query logs" vertex="1">
          <mxGeometry relative="1" x="-0.3615" y="-2" as="geometry">
            <mxPoint as="offset" />
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-13" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-12">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="386" y="220" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-51" connectable="0" parent="o_v1HXyxiM5dD5V4Gu-O-13" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];" value="user query" vertex="1">
          <mxGeometry relative="1" x="0.3485" y="-1" as="geometry">
            <mxPoint as="offset" />
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-2" parent="1" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.api_gateway;" value="&lt;span style=&quot;background-color: light-dark(#ffffff, var(--ge-dark-color, #121212));&quot;&gt;Amazon API Gateway&lt;/span&gt;" vertex="1">
          <mxGeometry height="78" width="78" x="210" y="180" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-9" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-4" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-5">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-4" parent="1" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.kinesis_data_streams;" value="Amazon Kinesis Data Streams" vertex="1">
          <mxGeometry height="78" width="78" x="320" y="-30" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-11" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-5" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-10">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-5" parent="1" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.kinesis_data_firehose;" value="Amazon Kinesis Firehose" vertex="1">
          <mxGeometry height="78" width="78" x="500" y="-30" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-17" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-10" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-16">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-10" parent="1" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" value="AWS Lambda&lt;div&gt;&lt;i&gt;compress queries&lt;/i&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="78" width="78" x="670" y="-30" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-12" parent="1" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.elasticsearch_service;" value="Amazon OpenSearch Service" vertex="1">
          <mxGeometry height="78" width="78" x="440" y="90" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-15" parent="1" style="points=[[0,0],[0.25,0],[0.5,0],[0.75,0],[1,0],[1,0.25],[1,0.5],[1,0.75],[1,1],[0.75,1],[0.5,1],[0.25,1],[0,1],[0,0.75],[0,0.5],[0,0.25]];outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;container=1;pointerEvents=0;collapsible=0;recursiveResize=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_aws_step_functions_workflow;strokeColor=#CD2264;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#CD2264;dashed=0;" value="AWS Step Functions workflow" vertex="1">
          <mxGeometry height="780" width="640" x="850" y="-190" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-19" edge="1" parent="o_v1HXyxiM5dD5V4Gu-O-15" source="o_v1HXyxiM5dD5V4Gu-O-16" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-18">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-16" parent="o_v1HXyxiM5dD5V4Gu-O-15" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#7AA116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.s3;" value="Amazon S3&lt;div&gt;&lt;i&gt;RAW Logs&lt;/i&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="78" width="78" x="60" y="160" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-21" edge="1" parent="o_v1HXyxiM5dD5V4Gu-O-15" source="o_v1HXyxiM5dD5V4Gu-O-18" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-20">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-18" parent="o_v1HXyxiM5dD5V4Gu-O-15" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.glue;" value="AWS Glue&lt;div&gt;&lt;i&gt;consolidate&lt;/i&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="78" width="78" x="250" y="160" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-20" parent="o_v1HXyxiM5dD5V4Gu-O-15" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#7AA116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.s3;" value="Amazon S3&lt;div&gt;&lt;i&gt;Parquet&lt;/i&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="78" width="78" x="430" y="160" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-28" edge="1" parent="o_v1HXyxiM5dD5V4Gu-O-15" source="o_v1HXyxiM5dD5V4Gu-O-25" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-27">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-25" parent="o_v1HXyxiM5dD5V4Gu-O-15" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#7AA116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.s3;" value="Amazon S3&lt;div&gt;&lt;i&gt;clustered&lt;/i&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="78" width="78" x="250" y="356" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-27" parent="o_v1HXyxiM5dD5V4Gu-O-15" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.athena;" value="Amazon Athena&lt;div&gt;&lt;i&gt;top queries/cluster&lt;/i&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="78" width="78" x="60" y="356" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-33" parent="o_v1HXyxiM5dD5V4Gu-O-15" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#C925D1;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.dynamodb;" value="Amazon DynamoDB&lt;div&gt;&lt;i&gt;output trending queries&lt;/i&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="78" width="78" x="250" y="620" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-42" parent="o_v1HXyxiM5dD5V4Gu-O-15" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.glue_crawlers;" value="Crawler" vertex="1">
          <mxGeometry height="48" width="48" x="75" y="80" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-43" parent="o_v1HXyxiM5dD5V4Gu-O-15" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.glue_crawlers;" value="Crawler" vertex="1">
          <mxGeometry height="48" width="48" x="445" y="80" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-46" parent="o_v1HXyxiM5dD5V4Gu-O-15" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.glue_data_catalog;" value="Catalog" vertex="1">
          <mxGeometry height="41.17" width="38" x="80" y="290" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-47" parent="o_v1HXyxiM5dD5V4Gu-O-15" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.glue_data_catalog;" value="Catalog" vertex="1">
          <mxGeometry height="41.17" width="38" x="450" y="290" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-26" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-22" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-25">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-22" parent="1" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.glue;" value="&amp;nbsp;AWS Glue&lt;div&gt;&lt;i&gt;K-means Job&lt;/i&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="78" width="78" x="1280" y="166" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-24" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-20" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-22">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="1420" y="9" />
              <mxPoint x="1420" y="205" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-32" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-29" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;startArrow=open;startFill=0;" target="o_v1HXyxiM5dD5V4Gu-O-31">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="1044" y="389" />
              <mxPoint x="1044" y="331" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-29" parent="1" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" value="AWS Lambda&lt;div&gt;&lt;i&gt;invoke Amazon Bedrock LLM&lt;/i&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="78" width="78" x="910" y="350" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-30" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-27" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-29">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="880" y="205" />
              <mxPoint x="880" y="389" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-31" parent="1" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#01A88D;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.bedrock;" value="Amazon Bedrock&lt;div&gt;&lt;i&gt;top queries classification&lt;/i&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="78" width="78" x="1100" y="292" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-34" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-29" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=0;entryY=0.75;entryDx=0;entryDy=0;entryPerimeter=0;" target="o_v1HXyxiM5dD5V4Gu-O-33">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="1044" y="410" />
              <mxPoint x="1044" y="488" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-37" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-35" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-36">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-35" parent="1" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.eventbridge;" value="EventBridge" vertex="1">
          <mxGeometry height="78" width="78" x="550" y="360" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-38" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-36" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;" target="o_v1HXyxiM5dD5V4Gu-O-15">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="830" y="400" />
              <mxPoint x="830" y="400" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-52" connectable="0" parent="o_v1HXyxiM5dD5V4Gu-O-38" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];" value="invoke" vertex="1">
          <mxGeometry relative="1" x="-0.1801" y="-3" as="geometry">
            <mxPoint y="-14" as="offset" />
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-36" parent="1" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#E7157B;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.eventbridge_scheduler;" value="Scheduler" vertex="1">
          <mxGeometry height="78" width="78" x="690" y="360" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-39" parent="1" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" value="&lt;span style=&quot;background-color: rgb(255, 255, 255);&quot;&gt;AWS Lambda&lt;/span&gt;" vertex="1">
          <mxGeometry height="78" width="78" x="398" y="272" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-40" edge="1" parent="1" source="o_v1HXyxiM5dD5V4Gu-O-39" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;entryX=1;entryY=0.75;entryDx=0;entryDy=0;entryPerimeter=0;" target="o_v1HXyxiM5dD5V4Gu-O-2">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="437" y="240" />
              <mxPoint x="343" y="240" />
              <mxPoint x="343" y="239" />
            </Array>
          </mxGeometry>
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-44" parent="1" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.glue_crawlers;" value="Crawler" vertex="1">
          <mxGeometry height="48" width="48" x="1115" y="90" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-45" parent="1" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.glue_data_catalog;" value="Catalog" vertex="1">
          <mxGeometry height="41.17" width="38" x="1120" y="-110" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-48" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="Search&amp;nbsp;&lt;div&gt;query&lt;/div&gt;" vertex="1">
          <mxGeometry height="30" width="70" x="80" y="185" as="geometry" />
        </mxCell>
        <mxCell id="o_v1HXyxiM5dD5V4Gu-O-49" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="content analysis" vertex="1">
          <mxGeometry height="30" width="60" x="90" y="315" as="geometry" />
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

### Notable patterns

- **Step Functions workflow as container**: The main batch orchestration is wrapped in a `group_aws_step_functions_workflow` container (850x640px, ID `o_v1HXyxiM5dD5V4Gu-O-15`) with `container=1` and `pointerEvents=0`. All workflow steps (S3, Glue, Athena, DynamoDB) are children of this group with relative coordinates inside the 640px-wide workflow boundary.
- **Sub-resource icons positioned above service icons**: Glue Crawlers (48x48px, `shape=mxgraph.aws4.glue_crawlers`) and Glue Data Catalogs (38x41px, `shape=mxgraph.aws4.glue_data_catalog`) are positioned directly above their associated S3 buckets or Glue services, creating visual sub-component relationships without explicit parent-child XML nesting.
- **Edge labels as child cells with connectable=0**: Three edges include inline text labels using child `mxCell` elements with `connectable="0"` and `style="edgeLabel;..."` (e.g., "query logs", "user query", "invoke"). The `relative="1"` geometry positions them along the edge path using offset coordinates.
- **Bidirectional edge with startArrow=open**: The Lambda-to-Bedrock connection (ID `o_v1HXyxiM5dD5V4Gu-O-32`) uses `startArrow=open;startFill=0` to show a two-way invocation pattern, distinguishing the LLM request-response flow from unidirectional data flows.
- **EventBridge split into service + scheduler**: EventBridge uses two nodes: the main service icon (`resIcon=mxgraph.aws4.eventbridge`) and a separate EventBridge Scheduler sub-resource (`shape=mxgraph.aws4.eventbridge_scheduler`), connected sequentially to show schedule-driven Step Functions invocation.
- **Feedback loop with complex routing**: DynamoDB output (ID `o_v1HXyxiM5dD5V4Gu-O-33`) routes back to a Lambda (ID `o_v1HXyxiM5dD5V4Gu-O-39`) and then to API Gateway using a long edge with three `mxPoint` waypoints (1210,469 → 1210,550 → 437,550), creating a U-shaped return path that avoids crossing the forward pipeline.
- **Text-only annotation nodes**: Two plain text cells (IDs `o_v1HXyxiM5dD5V4Gu-O-48`, `o_v1HXyxiM5dD5V4Gu-O-49`) with `style="text;html=1;...strokeColor=none;fillColor=none"` provide "Search query" and "content analysis" labels near actors, demonstrating how to add non-editable descriptive text outside the service icon paradigm.

## Example 2: Bedrock AgentCore Healthcare Agent (Compact Layout)

**Architecture type**: Compact agent-based architecture with AWS Cloud group
**Key patterns**: Actor shape for user, OAuth bidirectional edges with waypoints, text annotations for flow descriptions, tool call list boxes

### Prompt

Generate this diagram that shows the architecture of an AI-powered healthcare appointment agent where a user interacts through a conversational interface backed by Amazon Bedrock AgentCore Gateway, which connects to MCP tools exposed via OpenAPI specs, with authentication/identity management on one side and a FHIR-compliant health data store on the other. Include the flow from user authentication through the agent's decision-making to the backend services that handle immunization records, schedules, and appointment booking.

### Full XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="Electron" agent="Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/29.6.1 Chrome/142.0.7444.265 Electron/39.8.0 Safari/537.36" version="29.6.1">
  <diagram name="Page-1" id="j8CMlkFL6P3TrcBhnk5h">
    <mxGraphModel dx="692" dy="1392" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="850" pageHeight="1100" background="#FFFFFF" math="0" shadow="0">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />
        <mxCell id="dGBQkeyt1rKohwzD1Iis-1" parent="1" style="shape=actor;whiteSpace=wrap;html=1;" value="" vertex="1">
          <mxGeometry height="50" width="40" x="40" y="180" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-3" parent="1" style="points=[[0,0],[0.25,0],[0.5,0],[0.75,0],[1,0],[1,0.25],[1,0.5],[1,0.75],[1,1],[0.75,1],[0.5,1],[0.25,1],[0,1],[0,0.75],[0,0.5],[0,0.25]];outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;container=1;pointerEvents=0;collapsible=0;recursiveResize=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_aws_cloud_alt;strokeColor=#232F3E;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#16191F;dashed=0;" value="AWS Cloud" vertex="1">
          <mxGeometry height="400" width="890" x="160" y="70" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-8" parent="dGBQkeyt1rKohwzD1Iis-3" style="rounded=0;whiteSpace=wrap;html=1;" value="" vertex="1">
          <mxGeometry height="140" width="180" x="60" y="60" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-2" parent="dGBQkeyt1rKohwzD1Iis-3" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#01A88D;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.bedrock;" value="Amazon Bedrock&lt;div&gt;LLMs&lt;/div&gt;" vertex="1">
          <mxGeometry height="48" width="48" x="40" y="310" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-4" parent="dGBQkeyt1rKohwzD1Iis-3" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#DD344C;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.cognito;" value="Amazon Cognito" vertex="1">
          <mxGeometry height="50" width="50" x="180" y="308" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-5" parent="dGBQkeyt1rKohwzD1Iis-3" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.api_gateway;" value="Amazon&lt;div&gt;API Gateway&lt;/div&gt;" vertex="1">
          <mxGeometry height="60" width="60" x="560" y="84" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-6" parent="dGBQkeyt1rKohwzD1Iis-3" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#01A88D;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.healthlake;" value="AWS HeathLake" vertex="1">
          <mxGeometry height="56" width="56" x="740" y="84" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-7" parent="dGBQkeyt1rKohwzD1Iis-3" style="image;sketch=0;aspect=fixed;html=1;points=[];align=center;fontSize=12;image=img/lib/mscae/Genomics_Accounts.svg;" value="Healthcare Agent" vertex="1">
          <mxGeometry height="50" width="26" x="137" y="110" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-9" parent="dGBQkeyt1rKohwzD1Iis-3" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="&lt;b&gt;Strands or Langgraph Agent&lt;/b&gt;" vertex="1">
          <mxGeometry height="30" width="167.25" x="66.38" y="70" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-11" parent="dGBQkeyt1rKohwzD1Iis-3" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#01A88D;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.bedrock_agentcore;" value="AgentCore Identity" vertex="1">
          <mxGeometry height="48" width="48" x="393" y="308" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-10" parent="dGBQkeyt1rKohwzD1Iis-3" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#01A88D;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.bedrock_agentcore;" value="AgentCore Gateway&lt;div&gt;&lt;br&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="54" width="54" x="390" y="87" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-13" edge="1" parent="dGBQkeyt1rKohwzD1Iis-3" style="endArrow=open;html=1;rounded=0;" value="">
          <mxGeometry height="50" relative="1" width="50" as="geometry">
            <mxPoint x="125" y="155" as="sourcePoint" />
            <mxPoint x="-70" y="155" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-15" parent="dGBQkeyt1rKohwzD1Iis-3" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="&lt;font style=&quot;font-size: 11px;&quot;&gt;Agent response&lt;/font&gt;" vertex="1">
          <mxGeometry height="30" width="90" x="-60" y="160" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-16" edge="1" parent="dGBQkeyt1rKohwzD1Iis-3" style="endArrow=none;dashed=1;html=1;rounded=0;" target="dGBQkeyt1rKohwzD1Iis-7" value="">
          <mxGeometry height="50" relative="1" width="50" as="geometry">
            <Array as="points">
              <mxPoint x="60" y="240" />
              <mxPoint x="150" y="240" />
            </Array>
            <mxPoint x="60" y="308" as="sourcePoint" />
            <mxPoint x="100" y="268" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-17" parent="dGBQkeyt1rKohwzD1Iis-3" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="I&lt;font style=&quot;font-size: 11px;&quot;&gt;nvokes LLM and processes outputs&lt;/font&gt;" vertex="1">
          <mxGeometry height="30" width="97" x="50" y="210" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-18" edge="1" parent="dGBQkeyt1rKohwzD1Iis-3" source="dGBQkeyt1rKohwzD1Iis-4" style="html=1;labelBackgroundColor=#ffffff;startArrow=open;startFill=0;startSize=6;endArrow=open;endFill=0;endSize=6;jettySize=auto;orthogonalLoop=1;strokeWidth=1;dashed=1;fontSize=14;rounded=0;entryX=0.806;entryY=1.007;entryDx=0;entryDy=0;entryPerimeter=0;" target="dGBQkeyt1rKohwzD1Iis-8" value="">
          <mxGeometry height="60" relative="1" width="60" as="geometry">
            <mxPoint x="170" y="260" as="sourcePoint" />
            <mxPoint x="230" y="200" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-19" parent="dGBQkeyt1rKohwzD1Iis-3" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="oAuth 2.0 Ingress (Auth user call)" vertex="1">
          <mxGeometry height="30" width="100" x="210" y="230" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-20" edge="1" parent="dGBQkeyt1rKohwzD1Iis-3" style="html=1;labelBackgroundColor=#ffffff;startArrow=open;startFill=0;startSize=6;endArrow=open;endFill=0;endSize=6;jettySize=auto;orthogonalLoop=1;strokeWidth=1;dashed=1;fontSize=14;rounded=0;" target="dGBQkeyt1rKohwzD1Iis-10" value="">
          <mxGeometry height="60" relative="1" width="60" as="geometry">
            <Array as="points">
              <mxPoint x="320" y="330" />
              <mxPoint x="320" y="114" />
            </Array>
            <mxPoint x="230" y="330" as="sourcePoint" />
            <mxPoint x="270" y="200" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-21" edge="1" parent="dGBQkeyt1rKohwzD1Iis-3" source="dGBQkeyt1rKohwzD1Iis-4" style="html=1;labelBackgroundColor=#ffffff;startArrow=open;startFill=0;startSize=6;endArrow=open;endFill=0;endSize=6;jettySize=auto;orthogonalLoop=1;strokeWidth=1;dashed=1;fontSize=14;rounded=0;entryX=0;entryY=0.75;entryDx=0;entryDy=0;entryPerimeter=0;exitX=1;exitY=0.75;exitDx=0;exitDy=0;exitPerimeter=0;" target="dGBQkeyt1rKohwzD1Iis-11" value="">
          <mxGeometry height="60" relative="1" width="60" as="geometry">
            <mxPoint x="250" y="447" as="sourcePoint" />
            <mxPoint x="250" y="340" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-25" edge="1" parent="dGBQkeyt1rKohwzD1Iis-3" source="dGBQkeyt1rKohwzD1Iis-10" style="html=1;labelBackgroundColor=#ffffff;startArrow=open;startFill=0;startSize=6;endArrow=open;endFill=0;endSize=6;jettySize=auto;orthogonalLoop=1;strokeWidth=1;dashed=1;fontSize=14;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;exitPerimeter=0;" target="dGBQkeyt1rKohwzD1Iis-5" value="">
          <mxGeometry height="60" relative="1" width="60" as="geometry">
            <mxPoint x="500" y="227" as="sourcePoint" />
            <mxPoint x="500" y="120" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-26" parent="dGBQkeyt1rKohwzD1Iis-3" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="OpenAPI Spec" vertex="1">
          <mxGeometry height="30" width="90" x="460" y="87" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-27" edge="1" parent="dGBQkeyt1rKohwzD1Iis-3" source="dGBQkeyt1rKohwzD1Iis-6" style="html=1;labelBackgroundColor=#ffffff;startArrow=open;startFill=0;startSize=6;endArrow=open;endFill=0;endSize=6;jettySize=auto;orthogonalLoop=1;strokeWidth=1;dashed=1;fontSize=14;rounded=0;exitX=0;exitY=0.5;exitDx=0;exitDy=0;exitPerimeter=0;" value="">
          <mxGeometry height="60" relative="1" width="60" as="geometry">
            <Array as="points">
              <mxPoint x="670" y="113.5" />
            </Array>
            <mxPoint x="730" y="113.5" as="sourcePoint" />
            <mxPoint x="620" y="113.5" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-28" parent="dGBQkeyt1rKohwzD1Iis-3" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="Health records in FHIR format" vertex="1">
          <mxGeometry height="30" width="90" x="640" y="80" as="geometry" />
        </mxCell>
        <mxCell id="O5gGC1Q6fR2_njgexaNP-1" parent="dGBQkeyt1rKohwzD1Iis-3" style="rounded=0;whiteSpace=wrap;html=1;" value="" vertex="1">
          <mxGeometry height="30" width="210" x="530" y="190" as="geometry" />
        </mxCell>
        <mxCell id="O5gGC1Q6fR2_njgexaNP-8" parent="dGBQkeyt1rKohwzD1Iis-3" style="rounded=0;whiteSpace=wrap;html=1;" value="" vertex="1">
          <mxGeometry height="30" width="210" x="530" y="270" as="geometry" />
        </mxCell>
        <mxCell id="O5gGC1Q6fR2_njgexaNP-9" parent="dGBQkeyt1rKohwzD1Iis-3" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;rounded=0;" value="Tool 3: get_available_slots()" vertex="1">
          <mxGeometry height="30" width="210" x="540" y="270" as="geometry" />
        </mxCell>
        <mxCell id="O5gGC1Q6fR2_njgexaNP-10" parent="dGBQkeyt1rKohwzD1Iis-3" style="rounded=0;whiteSpace=wrap;html=1;" value="" vertex="1">
          <mxGeometry height="30" width="210" x="530" y="310" as="geometry" />
        </mxCell>
        <mxCell id="O5gGC1Q6fR2_njgexaNP-11" parent="dGBQkeyt1rKohwzD1Iis-3" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;rounded=0;" value="Tool 4: book_appointments()" vertex="1">
          <mxGeometry height="30" width="210" x="540" y="310" as="geometry" />
        </mxCell>
        <mxCell id="O5gGC1Q6fR2_njgexaNP-12" parent="dGBQkeyt1rKohwzD1Iis-3" style="rounded=0;whiteSpace=wrap;html=1;" value="" vertex="1">
          <mxGeometry height="30" width="210" x="530" y="230" as="geometry" />
        </mxCell>
        <mxCell id="O5gGC1Q6fR2_njgexaNP-5" parent="dGBQkeyt1rKohwzD1Iis-3" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;rounded=0;" value="Tool 1: get_patient_emr()" vertex="1">
          <mxGeometry height="30" width="210" x="540" y="190" as="geometry" />
        </mxCell>
        <mxCell id="O5gGC1Q6fR2_njgexaNP-7" parent="dGBQkeyt1rKohwzD1Iis-3" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;rounded=0;" value="Tool 2: search_immunization_emr()" vertex="1">
          <mxGeometry height="30" width="210" x="540" y="230" as="geometry" />
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-22" edge="1" parent="dGBQkeyt1rKohwzD1Iis-3" source="dGBQkeyt1rKohwzD1Iis-11" style="html=1;labelBackgroundColor=#ffffff;startArrow=open;startFill=0;startSize=6;endArrow=open;endFill=0;endSize=6;jettySize=auto;orthogonalLoop=1;strokeWidth=1;dashed=1;fontSize=14;rounded=0;exitX=0.5;exitY=0;exitDx=0;exitDy=0;exitPerimeter=0;" value="">
          <mxGeometry height="60" relative="1" width="60" as="geometry">
            <Array as="points">
              <mxPoint x="416.63" y="196" />
            </Array>
            <mxPoint x="416.63" y="304" as="sourcePoint" />
            <mxPoint x="417" y="164" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-12" edge="1" parent="1" style="endArrow=open;html=1;rounded=0;entryX=-0.038;entryY=0.4;entryDx=0;entryDy=0;entryPerimeter=0;" target="dGBQkeyt1rKohwzD1Iis-7" value="">
          <mxGeometry height="50" relative="1" width="50" as="geometry">
            <mxPoint x="90" y="200" as="sourcePoint" />
            <mxPoint x="150" y="150" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-14" connectable="0" parent="dGBQkeyt1rKohwzD1Iis-12" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];" value="User question" vertex="1">
          <mxGeometry relative="1" x="-0.4563" y="3" as="geometry">
            <mxPoint x="-26" y="-10" as="offset" />
          </mxGeometry>
        </mxCell>
        <mxCell id="dGBQkeyt1rKohwzD1Iis-23" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="oAuth 2.0 Egress (Auth tool call)" vertex="1">
          <mxGeometry height="30" width="100" x="580" y="290" as="geometry" />
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

### Notable patterns

- **Actor shape for user**: A `shape=actor` element (id `dGBQkeyt1rKohwzD1Iis-1`) positioned outside the AWS Cloud group at x="40" y="180" represents the external user, creating clear visual separation between the user and cloud infrastructure.

- **Rectangle container for agent component**: The agent is represented by a plain rectangle container (id `dGBQkeyt1rKohwzD1Iis-8`, 180x140px) with a text label overlay reading "Strands or Langgraph Agent" (id `dGBQkeyt1rKohwzD1Iis-9`) and a healthcare agent icon (id `dGBQkeyt1rKohwzD1Iis-7`) placed inside it, demonstrating how to create labeled component groupings.

- **Bidirectional dashed edges with open arrows**: OAuth flows use `dashed=1` edges with `startArrow=open;startFill=0;endArrow=open;endFill=0` to show bidirectional communication. The edges connect Cognito (id `dGBQkeyt1rKohwzD1Iis-4`) to both the agent container and AgentCore Identity (id `dGBQkeyt1rKohwzD1Iis-11`), and from AgentCore Gateway to API Gateway.

- **labelBackgroundColor=#ffffff on edges**: All OAuth flow edges set `labelBackgroundColor=#ffffff` to ensure edge labels remain readable when crossing other elements or backgrounds, preventing visual clutter.

- **Tool call boxes with evenly spaced rectangles**: Four tool boxes are created as plain rectangles (height=30, width=210) at y-coordinates 190, 230, 270, 310 (40px intervals), each with an overlaid text cell containing the tool name. This pattern creates a clean vertical list without complex nesting.

- **Text annotations near edges**: Flow descriptions like "Invokes LLM and processes outputs" (id `dGBQkeyt1rKohwzD1Iis-17`), "Agent response" (id `dGBQkeyt1rKohwzD1Iis-15`), and "oAuth 2.0 Ingress" (id `dGBQkeyt1rKohwzD1Iis-19`) are positioned as separate text cells near their respective edges, using fontSize=11 for readability without overwhelming the diagram.

- **Waypoint routing to avoid label overlap**: The edge from AgentCore Identity (id `dGBQkeyt1rKohwzD1Iis-22`) routes vertically upward using a waypoint at (416.63, 196) to avoid overlapping the "AgentCore Gateway" label, demonstrating explicit control over edge paths in dense layouts.

## Example 3: Amazon DataZone Unified Data Catalog (Column Layout)

**Architecture type**: Column-based reference architecture with nested groups
**Key patterns**: Dense layout with 40px icons and fontSize=11, multiple container nesting levels, external data source icons, dashed column groupings

### Prompt

Generate this diagram that shows a unified data catalog architecture on AWS where data from various sources gets ingested, stored in data lakes and warehouses, and automatically cataloged with metadata. Amazon DataZone acts as the central hub where all metadata is organized, enriched with business context, and made discoverable. Users access a self-service portal to find, share, and govern data assets across the organization.

### Full XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<mxfile host="app.diagrams.net" agent="Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/145.0.0.0 Safari/537.36" version="29.6.1">
  <diagram name="Page-1" id="1l8y0xzAVzh28N7EnIor">
    <mxGraphModel dx="1566" dy="918" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1100" pageHeight="850" math="0" shadow="0" background="#FFFFFF">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />
        <mxCell id="qta-H_kxxToBczopar2c-4" parent="1" style="points=[[0,0],[0.25,0],[0.5,0],[0.75,0],[1,0],[1,0.25],[1,0.5],[1,0.75],[1,1],[0.75,1],[0.5,1],[0.25,1],[0,1],[0,0.75],[0,0.5],[0,0.25]];outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=11;fontStyle=0;container=1;pointerEvents=0;collapsible=0;recursiveResize=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_aws_cloud_alt;strokeColor=#232F3E;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#16191F;dashed=0;" value="AWS Cloud" vertex="1">
          <mxGeometry height="508.6" width="800" x="130" y="160" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-25" connectable="0" parent="qta-H_kxxToBczopar2c-4" style="group" value="" vertex="1">
          <mxGeometry height="460" width="210" x="580" y="9.99999999999999" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-21" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;strokeColor=light-dark(#8c4fff, #ededed);" value="" vertex="1">
          <mxGeometry height="460" width="210" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-92" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;strokeColor=light-dark(#5a6b86, #ededed);" value="" vertex="1">
          <mxGeometry height="36.5" width="188.5" x="11.5" y="83.5" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-23" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.datazone;" value="" vertex="1">
          <mxGeometry height="35" width="35" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-27" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.datazone_data_portal;" value="" vertex="1">
          <mxGeometry height="20" width="20" x="15" y="50" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-26" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Amazon DataZone domain" vertex="1">
          <mxGeometry height="30" width="143" x="40" y="2.5" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-28" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Amazon DataZone portal" vertex="1">
          <mxGeometry height="30" width="143" x="35" y="45" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-32" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="shape=image;html=1;verticalAlign=top;verticalLabelPosition=bottom;labelBackgroundColor=#ffffff;imageAspect=0;aspect=fixed;image=https://icons.diagrams.net/icon-cache1/Business___Finance_glyph_V6-2603/53_design_Tool_identity_draw_development_creative_skills_process-1444.svg" value="" vertex="1">
          <mxGeometry height="25" width="25" x="16" y="89.25" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-33" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="domain unit" vertex="1">
          <mxGeometry height="30" width="75.5" x="40" y="83.5" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-93" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#5A6B86;" value="" vertex="1">
          <mxGeometry height="320" width="188" x="12" y="130" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-94" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.datazone_data_projects;" value="" vertex="1">
          <mxGeometry height="20" width="20" x="16" y="140" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-106" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Amazon DataZone projects" vertex="1">
          <mxGeometry height="30" width="143" x="37.5" y="135" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-108" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=7;fontSize=11;" value="" vertex="1">
          <mxGeometry height="31" width="20" x="36" y="179" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-109" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="shape=image;html=1;verticalAlign=top;verticalLabelPosition=bottom;labelBackgroundColor=#ffffff;imageAspect=0;aspect=fixed;image=https://icons.diagrams.net/icon-cache1/User_interface-2289/73-files-817.svg" value="" vertex="1">
          <mxGeometry height="32" width="32" x="80" y="180" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-110" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;strokeColor=#232F3E;fillColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.checklist_cost;" value="" vertex="1">
          <mxGeometry height="50" width="50" x="132" y="175" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-113" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="custom assets" vertex="1">
          <mxGeometry height="30" width="70" x="11" y="215" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-114" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="metadata&lt;div&gt;forms&lt;/div&gt;" vertex="1">
          <mxGeometry height="30" width="70" x="61" y="215" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-115" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="business&lt;div&gt;glossaries&lt;/div&gt;" vertex="1">
          <mxGeometry height="30" width="70" x="115.5" y="216" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-116" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#5A6B86;fontColor=light-dark(#5b6b86, #ededed);dashed=1;" value="" vertex="1">
          <mxGeometry height="180" width="169.25" x="20.75" y="260" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-117" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Inventory enrichment" vertex="1">
          <mxGeometry height="30" width="143" x="29.25" y="260" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-118" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.aws_glue_data_quality;" value="" vertex="1">
          <mxGeometry height="25" width="25" x="37.5" y="293" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-119" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.datazone_business_data_catalog;" value="" vertex="1">
          <mxGeometry height="27.46" width="25" x="44" y="377.54" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-121" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="sketch=0;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#505050;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;outlineConnect=0;align=center;shape=mxgraph.office.databases.database_availability_group;" value="" vertex="1">
          <mxGeometry height="25" width="25" x="95.25" y="357" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-122" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#01A88D;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.sagemaker_model;" value="" vertex="1">
          <mxGeometry height="25" width="25" x="138" y="293" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-127" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="html=1;whiteSpace=wrap;shape=isoCube2;backgroundOutline=1;isoAngle=15;" value="" vertex="1">
          <mxGeometry height="25" width="25" x="147.25" y="392" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-128" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;rounded=0;fontSize=11;" value="AWS Glue Data&lt;div&gt;Quality scores&lt;/div&gt;" vertex="1">
          <mxGeometry height="35" width="111" x="22.25" y="318" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-129" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="AI-generated descriptions" vertex="1">
          <mxGeometry height="35" width="111" x="95" y="318" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-130" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="business&lt;div&gt;data catalog&lt;/div&gt;" vertex="1">
          <mxGeometry height="35" width="111" x="1" y="405.00000000000006" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-159" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="data lineage" vertex="1">
          <mxGeometry height="35" width="111" x="54.25" y="371" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-160" parent="YhFb5mMxXpx9Dc9dV3Cx-25" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="data products" vertex="1">
          <mxGeometry height="35" width="111" x="95" y="409" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-27" parent="qta-H_kxxToBczopar2c-4" style="rounded=0;whiteSpace=wrap;html=1;dashed=1;fillColor=none;fontSize=11;" value="" vertex="1">
          <mxGeometry height="472.8" width="190" x="160" y="17.2" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-10" edge="1" parent="qta-H_kxxToBczopar2c-4" source="qta-H_kxxToBczopar2c-35" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0.75;exitDx=0;exitDy=0;entryX=0.571;entryY=1.068;entryDx=0;entryDy=0;entryPerimeter=0;" target="YhFb5mMxXpx9Dc9dV3Cx-4">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-35" parent="qta-H_kxxToBczopar2c-4" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;fontSize=11;strokeColor=#5A6B86;" value="" vertex="1">
          <mxGeometry height="70" width="174" x="169" y="310" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-38" parent="qta-H_kxxToBczopar2c-4" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;fontSize=11;strokeColor=#5A6B86;" value="" vertex="1">
          <mxGeometry height="93" width="171" x="169" y="390" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-17" parent="qta-H_kxxToBczopar2c-4" style="rounded=0;whiteSpace=wrap;html=1;dashed=1;fillColor=none;fontSize=11;" value="" vertex="1">
          <mxGeometry height="460" width="120" x="10" y="30" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-8" edge="1" parent="qta-H_kxxToBczopar2c-4" source="qta-H_kxxToBczopar2c-28" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1.003;exitY=0.084;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;exitPerimeter=0;" target="qta-H_kxxToBczopar2c-47">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-28" parent="qta-H_kxxToBczopar2c-4" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;fontSize=11;strokeColor=light-dark(#5b6b86, #ededed);" value="" vertex="1">
          <mxGeometry height="166" width="175" x="167" y="120" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-7" parent="qta-H_kxxToBczopar2c-4" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.appflow;" value="" vertex="1">
          <mxGeometry height="40" width="40" x="50" y="83" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-8" parent="qta-H_kxxToBczopar2c-4" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.glue;" value="" vertex="1">
          <mxGeometry height="40" width="40" x="50" y="165" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-9" parent="qta-H_kxxToBczopar2c-4" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#C925D1;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.database_migration_service;" value="" vertex="1">
          <mxGeometry height="40" width="40" x="50" y="249" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-10" parent="qta-H_kxxToBczopar2c-4" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.kinesis;" value="" vertex="1">
          <mxGeometry height="40" width="40" x="50" y="335" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-11" parent="qta-H_kxxToBczopar2c-4" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.managed_streaming_for_kafka;" value="" vertex="1">
          <mxGeometry height="40" width="40" x="50" y="420" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-12" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Amazon AppFlow" vertex="1">
          <mxGeometry height="30" width="150" x="-2" y="119" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-13" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="AWS Glue" vertex="1">
          <mxGeometry height="30" width="150" x="-5" y="202" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-14" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="AWS DMS" vertex="1">
          <mxGeometry height="30" width="150" x="-5" y="285" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-15" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Amazon Kinesis" vertex="1">
          <mxGeometry height="30" width="150" x="-5" y="372" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-16" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Amazon MSK" vertex="1">
          <mxGeometry height="30" width="150" x="-2" y="460" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-18" parent="qta-H_kxxToBczopar2c-4" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.redshift;" value="" vertex="1">
          <mxGeometry height="40" width="40" x="231" y="41.2" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-19" parent="qta-H_kxxToBczopar2c-4" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#C925D1;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.aurora;" value="" vertex="1">
          <mxGeometry height="40" width="40" x="190" y="144" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-20" parent="qta-H_kxxToBczopar2c-4" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#C925D1;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.dynamodb;" value="" vertex="1">
          <mxGeometry height="40" width="40" x="270" y="144" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-21" parent="qta-H_kxxToBczopar2c-4" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=7;fontSize=11;" value="" vertex="1">
          <mxGeometry height="40" width="30" x="233" y="213" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-22" parent="qta-H_kxxToBczopar2c-4" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#7AA116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.s3;" value="" vertex="1">
          <mxGeometry height="40" width="40" x="294" y="320" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-23" parent="qta-H_kxxToBczopar2c-4" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#7AA116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.s3;" value="" vertex="1">
          <mxGeometry height="40" width="40" x="292" y="425.6" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-25" parent="qta-H_kxxToBczopar2c-4" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#434445;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;outlineConnect=0;align=center;shape=mxgraph.vvd.nsx_dashboard;fontSize=11;" value="" vertex="1">
          <mxGeometry height="37.2" width="40" x="173" y="428" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-30" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Amazon Aurora" vertex="1">
          <mxGeometry height="30" width="62" x="179" y="187" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-31" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Amazon DynamoDB" vertex="1">
          <mxGeometry height="30" width="62" x="259" y="186" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-32" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Amazon Redshift" vertex="1">
          <mxGeometry height="30" width="111" x="197.5" y="76.2" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-33" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="&lt;i&gt;data warehouse&lt;/i&gt;" vertex="1">
          <mxGeometry height="30" width="111" x="199" y="89" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-34" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Data storage" vertex="1">
          <mxGeometry height="30" width="111" x="198" y="13.2" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-36" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Amazon S3" vertex="1">
          <mxGeometry height="30" width="92" x="258" y="355" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-41" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;rounded=0;fontStyle=2;fontSize=11;" value="Unstructured data" vertex="1">
          <mxGeometry height="30" width="68" x="172" y="394" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-37" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;rounded=0;fontStyle=2;fontSize=11;" value="Structured and Semi-structured data" vertex="1">
          <mxGeometry height="30" width="92" x="178" y="330" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-39" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="ML models" vertex="1">
          <mxGeometry height="30" width="92" x="206.5" y="443.6" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-26" parent="qta-H_kxxToBczopar2c-4" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#01A88D;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.sagemaker_model;" value="" vertex="1">
          <mxGeometry height="40" width="40" x="229" y="410" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-43" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="third-party databases or data warehouses" vertex="1">
          <mxGeometry height="30" width="143" x="182" y="255" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-44" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Databases" vertex="1">
          <mxGeometry height="30" width="143" x="175.5" y="118" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-45" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Data lakes" vertex="1">
          <mxGeometry height="30" width="111" x="195.5" y="285" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-48" connectable="0" parent="qta-H_kxxToBczopar2c-4" style="group;fontSize=11;" value="" vertex="1">
          <mxGeometry height="150" width="210" x="360" y="160" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-47" parent="qta-H_kxxToBczopar2c-48" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;strokeColor=light-dark(#8c4fff, #ededed);fontSize=11;" value="" vertex="1">
          <mxGeometry height="150" width="210" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-46" parent="qta-H_kxxToBczopar2c-48" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#16191F;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.glue;" value="" vertex="1">
          <mxGeometry height="19.6875" width="19.6875" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-72" parent="qta-H_kxxToBczopar2c-48" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.glue_crawlers;" value="" vertex="1">
          <mxGeometry height="28.125" width="28.125" x="21.003333333333337" y="56.25" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-73" parent="qta-H_kxxToBczopar2c-48" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.glue_data_catalog;" value="" vertex="1">
          <mxGeometry height="28.125" width="25.96875" x="85.31833333333334" y="56.250000000000014" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-74" parent="qta-H_kxxToBczopar2c-48" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#8C4FFF;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.aws_glue_data_quality;" value="" vertex="1">
          <mxGeometry height="28.125" width="28.125" x="151.66666666666669" y="56.25" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-1" parent="qta-H_kxxToBczopar2c-48" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;rounded=0;fontSize=11;" value="AWS Glue&lt;div&gt;&lt;i&gt;import technical metadata assets&lt;/i&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="28.125" width="198.33333333333334" x="23.336666666666666" y="3.75" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-3" parent="qta-H_kxxToBczopar2c-48" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="AWS Glue Crawler" vertex="1">
          <mxGeometry height="28.125" width="62" x="7.330000000000041" y="89.0625" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-4" parent="qta-H_kxxToBczopar2c-48" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="AWS Glue Data Catalog" vertex="1">
          <mxGeometry height="28.125" width="70.67" x="63.83" y="89.0625" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-5" parent="qta-H_kxxToBczopar2c-48" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="AWS Glue Data Quality" vertex="1">
          <mxGeometry height="28.125" width="70.67" x="131.33000000000004" y="89.0625" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-49" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Data ingestion" vertex="1">
          <mxGeometry height="30" width="111" x="16" y="34" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-9" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="JDBC" vertex="1">
          <mxGeometry height="30" width="143" x="310" y="130" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-162" edge="1" parent="qta-H_kxxToBczopar2c-4" source="qta-H_kxxToBczopar2c-47" style="endArrow=open;endFill=0;html=1;rounded=0;exitX=1;exitY=0.75;exitDx=0;exitDy=0;entryX=0.007;entryY=0.414;entryDx=0;entryDy=0;entryPerimeter=0;" target="YhFb5mMxXpx9Dc9dV3Cx-93" value="">
          <mxGeometry height="50" relative="1" width="50" as="geometry">
            <mxPoint x="380" y="290" as="sourcePoint" />
            <mxPoint x="430" y="240" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-164" edge="1" parent="qta-H_kxxToBczopar2c-4" source="qta-H_kxxToBczopar2c-38" style="endArrow=open;endFill=0;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;" value="">
          <mxGeometry height="50" relative="1" width="50" as="geometry">
            <mxPoint x="510" y="420" as="sourcePoint" />
            <mxPoint x="580" y="436" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-165" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;rounded=0;fontSize=11;" value="catalog unstructured data as custom assets" vertex="1">
          <mxGeometry height="30" width="210" x="360" y="406" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-167" edge="1" parent="qta-H_kxxToBczopar2c-4" source="qta-H_kxxToBczopar2c-27" style="endArrow=open;endFill=0;html=1;rounded=0;exitX=1.004;exitY=0.109;exitDx=0;exitDy=0;exitPerimeter=0;entryX=0;entryY=0.128;entryDx=0;entryDy=0;entryPerimeter=0;" target="YhFb5mMxXpx9Dc9dV3Cx-21" value="">
          <mxGeometry height="50" relative="1" width="50" as="geometry">
            <mxPoint x="490" y="220" as="sourcePoint" />
            <mxPoint x="540" y="170" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-166" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;rounded=0;fontSize=11;fontStyle=2" value="import technical metadata assets" vertex="1">
          <mxGeometry height="30" width="180" x="375" y="41.2" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-168" edge="1" parent="qta-H_kxxToBczopar2c-4" style="endArrow=open;endFill=0;html=1;rounded=0;" value="">
          <mxGeometry height="50" relative="1" width="50" as="geometry">
            <mxPoint x="130.0000000000001" y="249.00333333333336" as="sourcePoint" />
            <mxPoint x="160" y="249" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-169" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="dashboards" vertex="1">
          <mxGeometry height="30" width="92" x="154" y="460" as="geometry" />
        </mxCell>
        <mxCell id="YhFb5mMxXpx9Dc9dV3Cx-170" parent="qta-H_kxxToBczopar2c-4" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;rounded=0;fontSize=11;" value="&lt;b&gt;Unified data catalog&lt;/b&gt;" vertex="1">
          <mxGeometry height="30" width="110" x="630" y="473.6" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-40" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Amazon S3" vertex="1">
          <mxGeometry height="30" width="92" x="387" y="619" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-50" parent="1" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=7;fontSize=11;" value="" vertex="1">
          <mxGeometry height="30" width="21.8" x="58.4" y="181" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-51" parent="1" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#232F3D;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.office_building;strokeWidth=1;" value="" vertex="1">
          <mxGeometry height="41.2" width="26.41" x="56.1" y="256" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-52" parent="1" style="sketch=0;outlineConnect=0;fontColor=#16191F;gradientColor=none;fillColor=#232F3D;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.data_stream;" value="" vertex="1">
          <mxGeometry height="38" width="38" x="51.2" y="333" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-54" parent="1" style="sketch=0;pointerEvents=1;shadow=0;dashed=0;html=1;strokeColor=none;fillColor=#505050;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;outlineConnect=0;align=center;shape=mxgraph.office.concepts.video_play;fontSize=11;" value="" vertex="1">
          <mxGeometry height="30" width="38.2" x="50.2" y="406" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-55" parent="1" style="shape=image;html=1;verticalAlign=top;verticalLabelPosition=bottom;labelBackgroundColor=#ffffff;imageAspect=0;aspect=fixed;image=https://icons.diagrams.net/icon-cache1/User_interface-2289/73-files-817.svg;fontSize=11;" value="" vertex="1">
          <mxGeometry height="36" width="36" x="51.2" y="461" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-56" parent="1" style="shape=image;html=1;verticalAlign=top;verticalLabelPosition=bottom;labelBackgroundColor=#ffffff;imageAspect=0;aspect=fixed;image=https://icons.diagrams.net/icon-cache1/Essential_Part_4-2571/356-Document_Code-766.svg;fontSize=11;" value="" vertex="1">
          <mxGeometry height="32" width="32" x="53.2" y="520" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-57" parent="1" style="sketch=0;verticalLabelPosition=bottom;sketch=0;aspect=fixed;html=1;verticalAlign=top;strokeColor=none;fillColor=#000000;align=center;outlineConnect=0;pointerEvents=1;shape=mxgraph.citrix2.web_saas_apps;fontSize=11;" value="" vertex="1">
          <mxGeometry height="30.76" width="40" x="49.2" y="576" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-58" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="SQL/NoSQL databases" vertex="1">
          <mxGeometry height="30" width="70" x="35.2" y="216" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-59" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="on-premises&lt;div&gt;databases&lt;/div&gt;" vertex="1">
          <mxGeometry height="30" width="70" x="35.2" y="297.2" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-60" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="streaming data" vertex="1">
          <mxGeometry height="30" width="70" x="34.2" y="372" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-61" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="media" vertex="1">
          <mxGeometry height="30" width="70" x="34.2" y="430" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-62" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="flat files" vertex="1">
          <mxGeometry height="30" width="70" x="32.2" y="491" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-63" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="logs" vertex="1">
          <mxGeometry height="30" width="70" x="34.2" y="547" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-64" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="SaaS applications" vertex="1">
          <mxGeometry height="30" width="70" x="35.2" y="613.76" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-65" parent="1" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;fontSize=11;strokeColor=#5A6B86;" value="" vertex="1">
          <mxGeometry height="491" width="80" x="30" y="160" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-66" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;fontSize=11;" value="Data sources" vertex="1">
          <mxGeometry height="30" width="111" x="16.7" y="155" as="geometry" />
        </mxCell>
        <mxCell id="qta-H_kxxToBczopar2c-71" edge="1" parent="1" style="endArrow=open;endFill=0;html=1;rounded=0;fontSize=11;" target="qta-H_kxxToBczopar2c-4" value="">
          <mxGeometry height="50" relative="1" width="50" as="geometry">
            <mxPoint x="110" y="410" as="sourcePoint" />
            <mxPoint x="430" y="370" as="targetPoint" />
          </mxGeometry>
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

### Notable patterns

- **Four-column layout with dashed borders**: Left column (Data sources) outside AWS Cloud, three internal columns (Data ingestion, Data storage, DataZone domain) inside AWS Cloud, all separated by `dashed=1` rectangles
- **Dense vertical stacking with 40px icons**: Data ingestion column shows 5 services (AppFlow, Glue, DMS, Kinesis, MSK) vertically stacked at 40px height with `fontSize=11` labels below
- **Multiple nesting levels**: DataZone domain contains domain unit box, which contains projects box, which contains dashed "Inventory enrichment" box with 25px sub-resource icons
- **External data source icons**: Left column uses non-AWS generic icons (cylinder for databases, building for on-premises, video player, file icons) to represent sources outside AWS
- **Service-level vs sub-resource shapes**: Main services use `shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.{name}` style (40px), enrichment icons use direct `shape=mxgraph.aws4.{name}` (25px)
- **Italic/bold typography for hierarchy**: Section headers use regular weight, italic text for sub-labels (e.g., "data warehouse"), bold for final summary label ("Unified data catalog")
- **Open arrow edges without labels**: All connections use `endArrow=open;endFill=0` style with no edge labels, keeping visual noise minimal in this dense diagram

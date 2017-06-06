# JavaServer Faces
## web.xml
### Context
```
<context-param>
  <param-name>javax.faces.PROJECT_STAGE</param-name>
  <param-value>Development</param-value>
</context-param>
```
### Servlet
```
<servlet>
  <servlet-name>Faces Servlet</servlet-name>
  <servlet-class>javax.faces.webapp.FacesServlet</servlet-class>
  <load-on-startup>1</load-on-startup>
</servlet>
<servlet-mapping>
  <servlet-name>Faces Servlet</servlet-name>
  <url-pattern>*.xhtml</url-pattern>
</servlet-mapping>
```
### Index
```
<welcome-file-list>
  <welcome-file>index.xhtml</welcome-file>
</welcome-file-list>
```
## Facelet
### Tag Libraries
| Tag Library | URI | Prefix |
| --- | --- | --- |
| JavaServer Faces Facelets Tag Library | http://xmlns.jcp.org/jsf/facelets | ui: |
| JavaServer Faces HTML Tag Library | http://xmlns.jcp.org/jsf/html | h: |
| JavaServer Faces Core Tag Library | http://xmlns.jcp.org/jsf/core | f: |
| Pass-through Elements Tag Library | http://xmlns.jcp.org/jsf | jsf: |
| Pass-through Attributes Tag Library| http://xmlns.jcp.org/jsf/passthrough| p: |
| Composite Component Tag Library | http://xmlns.jcp.org/jsf/composite | cc: |
| JSTL Core Tag Library | http://xmlns.jcp.org/jsp/jstl/core | c: |
| JSTL Functions Tag Library | http://xmlns.jcp.org/jsp/jstl/functions | fn: |

### Example
```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">

<html lang="en"
      xmlns="http://www.w3.org/1999/xhtml"
      xmlns:h="http://xmlns.jcp.org/jsf/html">

    <h:head>
        <h:outputStylesheet library="css" name="default.css"/>
        <title>Guess Number Facelets Application</title>
    </h:head>
    <h:body>
        <h:form>
            <h:graphicImage value="#{resource['images:wave.med.gif']}"
                            alt="Duke waving his hand"/>
            <h2>
                <h:outputText id="result" value="#{userNumberBean.response}"/>
            </h2>
            <h:commandButton id="back" value="Back" action="greeting"/>
        </h:form>
    </h:body>
</html>
```

## Managed Bean
```
@Named

@RequestScoped
@SessionScoped
@ApplicationScoped

@Model -> @Named + @RequestScoped
```

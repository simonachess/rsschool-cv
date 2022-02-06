#CV

## Personal details
**Simona Limontaite**
- Tel.: +37063975725
- Email: simona.limonte@gmail.com

## Summary
I am interested in entry level or junior front-end developer position.
I am working as a chess coach in Telsiai and online (in Lithuanian, Russian and English languages) at 
the moment. I believe that playing chess for more than 15 year I developed skills which helped me in a 
lot of fields. Analytical mindset and justification, visualization, concentration, creativeness,
decision-making, attention to details, ability to work in a team. My goal is to retrain myself to IT field.

## Skills
- HTML, CSS
- JavaScript
- Bootstrap
- Tailwind
- GitHub
- React
- MySQL

## Latest code example
```JSX
import React, {useState} from 'react'
import data from '../data/data'

export default function RenderTree() {

	const [active, setActive] = useState([])
	const [breadcrumbs, setBreadcrumbs] =useState([])
	
	const handleActiveNode = (node) =>{

		if(!active.includes(node.id)){
			if((node.id).length <= active.length){
				const copyActive = active.slice(0,(node.id).length-1)
				const copyBreadcrumb = breadcrumbs.slice(0,(node.id).length)
				setActive([...copyActive, node.id])
				setBreadcrumbs([...copyBreadcrumb, node.title])
			}else{
				setActive([...active, node.id])
				setBreadcrumbs([...breadcrumbs, node.title])
			}
		}
	}

	const handleShowFolders = (title) =>{
		if(!breadcrumbs.includes(title)){
			setBreadcrumbs([...breadcrumbs, title])
		}
	}

	const createMenu = (data) => {
		return (
			<ul>
				{data?.map((node, i) => {
					return (
						<li key={i} className='node'>
							<div onClick={()=>handleActiveNode(node)} >{node.title}</div>
							{node.nodes?.length > 0 && 
								<div className={`${active.includes(node.id) ? "" : "hidden-levels"}`}>{createMenu(node.nodes)}</div>}
								
						</li>
					)})}
			</ul>
		)
	}

	const menu = createMenu(data.Documents)

	return (
		<div className='container'>
			<ul className='breadcrumb-container'>
				{breadcrumbs.length > 0 && breadcrumbs.map((breacrumb, i)=>{
					return(
						<li key={i} className='breadcrumb'>{breacrumb}/</li>
					)
				})}
			</ul>
			<p onClick={()=>{handleShowFolders(Object.keys(data)[0])}} className='title'>{Object.keys(data)[0]}</p>
			 <div className={`${breadcrumbs.length > 0 ? "" : "hidden-breadcrumb"}`}>{menu}</div>
		</div>
	)
}
```
## Experience
Here is some of my works what I have learned https://github.com/simonachess.
I was doing internship in Corner Case Technology for 7 weeks.
I am doing internship at E-bros company at the moment.


## Education
I finished Baltic institute of technology Front-end courses
shecodes.io HTML, CSS, JavaScript, React courses
coursera.org Technical Support Fundamentals

## English
I am providing online chess lessons in English for about 3 years
